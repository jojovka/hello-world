# hello-world
Just my first repository


package kz.eub.moncl.screen.plannedwork;

import com.vaadin.ui.UI;
import io.jmix.core.DataManager;
import io.jmix.core.security.SystemAuthenticator;
import io.jmix.core.usersubstitution.CurrentUserSubstitution;
import io.jmix.ui.Notifications;
import io.jmix.ui.UiComponents;
import io.jmix.ui.component.DataGrid;
import io.jmix.ui.ScreenBuilders;
import io.jmix.ui.icon.Icons;
import io.jmix.ui.icon.JmixIcon;
import io.jmix.ui.model.CollectionContainer;
import io.jmix.ui.model.CollectionLoader;
import io.jmix.ui.screen.*;
import kz.eub.moncl.app.service.DisposableWorkService;
import kz.eub.moncl.app.service.PlannedWorkService;
import kz.eub.moncl.entity.DisposableTask;
import kz.eub.moncl.entity.DisposableTaskDTO;
import kz.eub.moncl.entity.PlannedWork;
import org.slf4j.Logger;
import org.springframework.beans.factory.annotation.Autowired;
import kz.eub.moncl.entity.EReportStatus;
import org.springframework.security.core.userdetails.UserDetails;

import java.net.URISyntaxException;
import java.security.KeyManagementException;
import java.security.KeyStoreException;
import java.security.NoSuchAlgorithmException;
import java.time.LocalDate;
import java.time.LocalDateTime;
import java.time.LocalTime;
import java.util.ArrayList;
import java.util.List;
import java.util.Timer;
import java.util.TimerTask;
import java.util.concurrent.atomic.AtomicBoolean;

@UiController("mcl_PlannedWork.browse")
@UiDescriptor("planned-work-browse.xml")
@LookupComponent("plannedWorksTable")
public class PlannedWorkBrowse extends StandardLookup<PlannedWork> {
    private static final Logger log = org.slf4j.LoggerFactory.getLogger(PlannedWorkBrowse.class);
    @Autowired
    private DataGrid<PlannedWork> plannedWorksTable;
    @Autowired
    private DataGrid<DisposableTask> disposableTasksTable;
    @Autowired
    private CollectionContainer<PlannedWork> plannedWorksDc;
    @Autowired
    private CollectionContainer<DisposableTaskDTO> disposableTasksDTODc;
    @Autowired
    private CurrentUserSubstitution currentUserSubstitution;
    @Autowired
    private PlannedWorkService plannedWorkService;
    @Autowired
    private DisposableWorkService disposableWorkService;
    @Autowired
    private DataManager dataManager;
    @Autowired
    private Notifications notifications;
    @Autowired
    private CollectionLoader<PlannedWork> plannedWorksDl;
//    @Autowired
//    private CollectionLoader<DisposableTask> disposableTasksDl;
    @Autowired
    private ScreenBuilders screenBuilders;
    @Autowired
    private SystemAuthenticator systemAuthenticator;
    @Autowired
    protected UiComponents uiComponents;

    private UI currentUI;
    private Timer timer;

    @Subscribe
    public void onInit(InitEvent event) throws URISyntaxException, KeyStoreException, NoSuchAlgorithmException, KeyManagementException {
        String authKey = disposableWorkService.zabbixAuth();
        List<DisposableTaskDTO> disposableTaskDTOList = new ArrayList<>();
        disposableTaskDTOList.addAll(disposableWorkService.triggerGet(authKey));

        disposableTasksDTODc.setItems(disposableTaskDTOList);
        disposableTasksTable.repaint();

        //Update table every minute using timer
        refreshData();

        plannedWorksTable.getColumnNN("priority")
                .setStyleProvider(plannedWork -> {
                    switch (plannedWork.getPriority()) {
                        case MEDIUM:
                            return "low-priority";
                        case HIGH:
                            return "mid-priority";
                        case HIGHEST:
                            return "high-priority";
                        default:
                            return null;
                    }
                });

        disposableTasksTable.getColumnNN("priority")
                .setStyleProvider(PlannedWork -> {
                    switch (PlannedWork.getPriority()) {
                        case MEDIUM:
                            return "low-priority";
                        case HIGH:
                            return "mid-priority";
                        case HIGHEST:
                            return "high-priority";
                        default:
                            return null;
                    }
                });

        //<----------Planned Work---------->
        //<----------Start Button---------->
        AtomicBoolean flagCheck = new AtomicBoolean(true);
        loadPlannedWorksDL();
        UserDetails user = currentUserSubstitution.getAuthenticatedUser();
        DataGrid.ButtonRenderer<PlannedWork> gridButtonRendererPlannedWorksButtonStart =
                getApplicationContext().getBean(DataGrid.ButtonRenderer.class);
        gridButtonRendererPlannedWorksButtonStart.setRendererClickListener(
                clickableRendererClickEvent -> {
                    PlannedWork plannedWorkStartItem = clickableRendererClickEvent.getItem();
                    if (plannedWorksDc.getItem(plannedWorkStartItem.getId()).getStatus().equals(EReportStatus.APPOINTED)) {
                        plannedWorksDc.getItem(plannedWorkStartItem.getId()).setStatus(EReportStatus.IN_PROCESS);
                        plannedWorksDc.getItem(plannedWorkStartItem.getId()).setActualStartTime(LocalTime.now().withNano(0));
                        LocalDateTime actualStartDateTime = LocalDate.now().atTime(plannedWorksDc.getItem(plannedWorkStartItem.getId()).getActualStartTime());
                        plannedWorksDc.getItem(plannedWorkStartItem.getId()).setFullName(user.getUsername());
                        int lastVersionedItem = plannedWorkStartItem.getVersion();
                        plannedWorksDc.getItem(plannedWorkStartItem.getId()).setVersion(lastVersionedItem);//Обновление optimistic lock
                        dataManager.save(plannedWorksDc.getItem(plannedWorkStartItem.getId()));
                        plannedWorksDl.load();

                        plannedWorksTable.repaint();
                    } else {
                        notifications.create()
                                .withCaption("Невозможно начать выполнение плановой работы")
                                .withDescription("Работа была начата или завершена")
                                .show();
                    }
                });
        this.plannedWorksTable.getColumn("btnStart")
                .setRenderer(gridButtonRendererPlannedWorksButtonStart);
        //</----------Start Button---------->

        //<----------Finish Button---------->
        DataGrid.ButtonRenderer<PlannedWork> gridButtonRendererButtonFinish =
                getApplicationContext().getBean(DataGrid.ButtonRenderer.class);
        gridButtonRendererButtonFinish.setRendererClickListener(
                clickableRendererClickEvent -> {
                    AtomicBoolean lateEndFlag = new AtomicBoolean(false);
                    PlannedWork plannedWorkEndItem = clickableRendererClickEvent.getItem();
                    if (plannedWorksDc.getItem(plannedWorkEndItem.getId()).getStatus().equals(EReportStatus.IN_PROCESS)) {
                        plannedWorksDc.getItem(plannedWorkEndItem.getId()).setStatus(EReportStatus.FINISHED);
                        plannedWorksDc.getItem(plannedWorkEndItem.getId()).setActualEndTime(LocalTime.now().withNano(0));
                        int versionWithoutComment = plannedWorkEndItem.getVersion();
                        plannedWorksDc.getItem(plannedWorkEndItem.getId()).setVersion(versionWithoutComment);
                        dataManager.save(plannedWorksDc.getItem(plannedWorkEndItem.getId()));
                        LocalDateTime actualEndDateTime = LocalDate.now().atTime(plannedWorksDc.getItem(plannedWorkEndItem.getId()).getActualEndTime());
                        if (actualEndDateTime.isAfter((plannedWorksDc.getItem(plannedWorkEndItem.getId()).getScheduledEndDateTime())))
                            lateEndFlag.set(true);
                        if (lateEndFlag.get() == flagCheck.get()) {
                            screenBuilders.editor(PlannedWork.class, this)
                                    .editEntity(plannedWorksDc.getItem(plannedWorkEndItem.getId()))
                                    .withOpenMode(OpenMode.DIALOG)
                                    .build()
                                    .show();
                            plannedWorksDl.load();
                            plannedWorksTable.repaint();
                        } else {
                            int versionWithComment = clickableRendererClickEvent.getItem().getVersion();
                            plannedWorksDc.getItem(plannedWorkEndItem.getId()).setVersion(versionWithComment);//Обновление optimistic lock
                            plannedWorkService.setFinishedPlannedWorkToReport(plannedWorksDc.getItem(plannedWorkEndItem.getId()));
                            plannedWorksDl.load();
                            plannedWorksTable.repaint();
                        }
                    } else {
                        notifications.create()
                                .withCaption("Невозможно завершить выполнение плановой работы")
                                .withDescription("Работа не была начата или уже завершена")
                                .show();
                    }
                });
        this.plannedWorksTable.getColumn("btnFinish")
                .setRenderer(gridButtonRendererButtonFinish);
        //</----------Finish Button---------->
        //</----------Planned Work---------->


        //<----------Disposable Work---------->
        //<----------Start Button---------->
//        loadDisposableWorksDL();
//        DataGrid.ButtonRenderer<DisposableTask> gridButtonRendererDisposableWorkButtonStart =
//                getApplicationContext().getBean(DataGrid.ButtonRenderer.class);
//        gridButtonRendererDisposableWorkButtonStart.setRendererClickListener(
//                clickableRendererClickEvent -> {
//                    DisposableTask disposableTaskStartItem = clickableRendererClickEvent.getItem();
//                    if (disposableTasksDTODc.getItem(disposableTaskStartItem.getId()).getStatus().equals(EReportStatus.APPOINTED)) {
//                        disposableTasksDc.getItem(disposableTaskStartItem.getId()).setStatus(EReportStatus.IN_PROCESS);
//                        disposableTasksDc.getItem(disposableTaskStartItem.getId()).setActualStartTime(LocalTime.now().withNano(0));
//                        disposableTasksDc.getItem(disposableTaskStartItem.getId()).setFullName(user.getUsername());
//                        int lastVersionedItem = clickableRendererClickEvent.getItem().getVersion();
//                        disposableTasksDc.getItem(disposableTaskStartItem.getId()).setVersion(lastVersionedItem);//Обновление optimistic lock
//                        dataManager.save(disposableTasksDc.getItem(disposableTaskStartItem.getId()));
//                        disposableTasksDl.load();
//                        disposableTasksTable.repaint();
//                    } else {
//                        notifications.create()
//                                .withCaption("Невозможно начать выполнение разовой задачи")
//                                .withDescription("Задача была начата или завершена")
//                                .show();
//                    }
//                });
//        this.disposableTasksTable.getColumn("btnStartDisposableTask")
//                .setRenderer(gridButtonRendererDisposableWorkButtonStart);
//        //</----------Start Button---------->
//
//        //<----------Finish Button---------->
//        DataGrid.ButtonRenderer<DisposableTask> gridButtonRendererDisposableWorkButtonFinish =
//                getApplicationContext().getBean(DataGrid.ButtonRenderer.class);
//        gridButtonRendererDisposableWorkButtonFinish.setRendererClickListener(
//                clickableRendererClickEvent -> {
//                    DisposableTask disposableTaskEndItem = clickableRendererClickEvent.getItem();
//                    if (disposableTasksDc.getItem(disposableTaskEndItem.getId()).getStatus().equals(EReportStatus.IN_PROCESS)) {
//                        disposableTasksDc.getItem(disposableTaskEndItem.getId()).setStatus(EReportStatus.FINISHED);
//                        disposableTasksDc.getItem(disposableTaskEndItem.getId()).setActualEndTime(LocalTime.now().withNano(0));
//                        dataManager.save(disposableTasksDc.getItem(disposableTaskEndItem.getId()));
//                        disposableTasksTable.repaint();
//                        plannedWorkService.setFinishedDisposableWorkToReport(disposableTasksDc.getItem(disposableTaskEndItem.getId()));
//                        disposableTasksDl.load();
//                    } else {
//                        notifications.create()
//                                .withCaption("Невозможно начать выполнение разовой задачи")
//                                .withDescription("Задача была начата или завершена")
//                                .show();
//                    }
//                });
//        this.disposableTasksTable.getColumn("btnFinishDisposableTask")
//                .setRenderer(gridButtonRendererDisposableWorkButtonFinish);
        //</----------Finish Button---------->
        //</-----------Disposable Work---------->
    }

    private void loadPlannedWorksDL() {
        plannedWorksDl.setQuery("select p from mcl_PlannedWork as p where p.status=:status or p.status=:status1");
        plannedWorksDl.setParameter("status", EReportStatus.APPOINTED);
        plannedWorksDl.setParameter("status1", EReportStatus.IN_PROCESS);
    }

//    private void loadDisposableWorksDL() {
//        disposableTasksDl.setQuery("select p from mcl_DisposableTask as p where (p.status=:status or p.status=:status1) or (p.status=:status3 and p.date>=:currentDate)");
//        disposableTasksDl.setParameter("status", EReportStatus.APPOINTED);
//        disposableTasksDl.setParameter("status1", EReportStatus.IN_PROCESS);
//        disposableTasksDl.setParameter("status3", EReportStatus.FINISHED);
//        disposableTasksDl.setParameter("currentDate", LocalDate.now());
//    }

    @Install(to = "plannedWorksTable.btnFinish", subject = "columnGenerator")
    private Icons.Icon plannedWorksTableBtnFinishColumnGenerator
            (DataGrid.ColumnGeneratorEvent<PlannedWork> columnGeneratorEvent) {
        return JmixIcon.STOP;
    }

    @Install(to = "plannedWorksTable.btnStart", subject = "columnGenerator")
    private Icons.Icon plannedWorksTableBtnStartColumnGenerator
            (DataGrid.ColumnGeneratorEvent<PlannedWork> columnGeneratorEvent) {
        return JmixIcon.PLAY;
    }

//    @Install(to = "disposableTasksTable.btnFinishDisposableTask", subject = "columnGenerator")
//    private Icons.Icon disposableTasksTableBtnFinishColumnGenerator
//            (DataGrid.ColumnGeneratorEvent<DisposableTask> columnGeneratorEvent) {
//        return JmixIcon.STOP;
//    }
//
//    @Install(to = "disposableTasksTable.btnStartDisposableTask", subject = "columnGenerator")
//    private Icons.Icon disposableTasksTableBtnStartColumnGenerator
//            (DataGrid.ColumnGeneratorEvent<DisposableTask> columnGeneratorEvent) {
//        return JmixIcon.PLAY;
//    }

    @Install(to = "plannedWorksTable", subject = "rowStyleProvider")
    private String styledGridRowStyleProvider(PlannedWork plannedWork) {
        if (LocalDateTime.now().isAfter(plannedWork.getScheduledStartDateTime().minusMinutes(10)) && LocalDateTime.now().isBefore(plannedWork.getScheduledStartDateTime())) {
            return "ten-minutes";
        } else if (LocalDateTime.now().isAfter(plannedWork.getScheduledEndDateTime())) {
            return "late";
        }else if (LocalDateTime.now().isAfter(plannedWork.getScheduledStartDateTime()) && LocalDateTime.now().isBefore(plannedWork.getScheduledEndDateTime())) {
            return "started";
        }
        return null;
    }

    @Subscribe
    public void onBeforeClose(BeforeCloseEvent event) {
        log.info("Updating data canceled");
        timer.cancel();
    }

    private void refreshData(){
        currentUI = UI.getCurrent();
        timer = new Timer();
        timer.schedule(new TimerTask() {
            @Override
            public void run() {
                systemAuthenticator.withSystem(()->{
                    log.info("Starting update PlannedWorkBrowse UI...");
                    currentUI.access(() ->{
                        plannedWorksDl.load();
                        currentUI.getCurrent().push();
                    });
                    log.info("finished update PlannedWorkBrowse UI");
                    return null;
                });
            }
        }, 0, 60*1000);
    }
}
