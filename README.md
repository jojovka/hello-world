# hello-world
Just my first repository

    package kz.eub.report360.screen.credreg;

import com.google.common.base.CaseFormat;
import io.jmix.core.DataManager;
import io.jmix.core.FileRef;
import io.jmix.core.FileStorage;
import io.jmix.core.Messages;
import io.jmix.ui.Notifications;
import io.jmix.ui.component.FileStorageUploadField;
import io.jmix.ui.component.SingleFileUploadField;
import io.jmix.ui.screen.*;
import kz.eub.report360.entity.Credreg;
import org.dhatim.fastexcel.reader.ReadableWorkbook;
import org.dhatim.fastexcel.reader.Sheet;
import org.springframework.beans.factory.annotation.Autowired;

import java.io.IOException;
import java.io.InputStream;
import java.lang.reflect.InvocationTargetException;
import java.lang.reflect.Method;
import java.util.ArrayList;
import java.util.Date;
import java.util.List;
import java.util.Objects;
import java.util.concurrent.atomic.AtomicInteger;
import java.util.concurrent.atomic.AtomicReference;
import java.util.stream.Stream;

import org.dhatim.fastexcel.reader.*;

@UiController("r360_Credreg.browse")
@UiDescriptor("credreg-browse.xml")
@LookupComponent("credregsTable")
public class CredregBrowse extends StandardLookup<Credreg> {

    @Autowired
    private FileStorageUploadField attachmentFileField;
    @Autowired
    private Notifications notifications;
    @Autowired
    private Messages messages;
    @Autowired
    private FileStorage fileStorage;
    @Autowired
    private DataManager dataManager;

@Subscribe("attachmentFileField")
    public void onAttachmentFileFieldFileUploadSucceed(SingleFileUploadField.FileUploadSucceedEvent event) {
        FileRef fileRef = attachmentFileField.getValue();
        if (fileRef != null) {
            try {
                try (InputStream is = fileStorage.openStream(fileRef)) {
                    try (ReadableWorkbook wb = new ReadableWorkbook(is)) {
                        Sheet sheet = wb.getFirstSheet();
                        try (Stream<Row> rows = sheet.openStream()) {
                            List<Credreg> batch = new ArrayList<>(5000);
                            rows.skip(2)
                                    .forEach(row -> {
                                        Credreg credreg = dataManager.create(Credreg.class);

                                        Cell cell0 = row.getCell(0);
                                        Cell cell1 = row.getCell(1);
                                        Cell cell2 = row.getCell(2);
                                        Cell cell5 = row.getCell(5);
                                        Cell cell6 = row.getCell(6);
                                        Cell cell7 = row.getCell(7);
                                        Cell cell8 = row.getCell(8);
                                        Cell cell9 = row.getCell(9);
                                        Cell cell10 = row.getCell(10);

                                        if (cell0.getType() != CellType.EMPTY){
                                            credreg.setSourceSystem(cell0.asString());
                                        } else if (cell0.getType() == CellType.EMPTY) {
                                            credreg.setSourceSystem("");
                                        }

                                        if (cell1.getType() != CellType.EMPTY){
                                            credreg.setOperationDate(cell1.asDate().toLocalDate());
                                        } else if (cell1.getType() == CellType.EMPTY) {
                                            credreg.setOperationDate(null);
                                        }

                                        if (cell2.getType() != CellType.EMPTY){
                                            credreg.setPrimaryContractNo(cell2.asString());
                                        } else if (cell2.getType() == CellType.EMPTY) {
                                            credreg.setPrimaryContractNo("");
                                        }

                                        if (cell5.getType() != CellType.EMPTY){
                                            credreg.setContractS(cell5.asNumber().longValue());
                                        }else if (cell5.getType() == CellType.EMPTY) {
                                            credreg.setContractS(null);
                                        }

                                        if (cell6.getType() != CellType.EMPTY){
                                            credreg.setTurnoverIntAmount(cell6.asNumber().longValue());
                                        } else if (cell6.getType() == CellType.EMPTY){
                                            credreg.setTurnoverIntAmount(null);
                                        }

                                        if (cell7.getType() != CellType.EMPTY){
                                            credreg.setTurnoverIntAmountCur(cell7.asNumber().longValue());
                                        } else if (cell7.getType() == CellType.EMPTY){
                                            credreg.setTurnoverIntAmountCur(null);
                                        }

                                        if (cell8.getType() != CellType.EMPTY){
                                            credreg.setTurnoverDebAmount(cell8.asNumber().longValue());
                                        } else if (cell8.getType() == CellType.EMPTY){
                                            credreg.setTurnoverDebAmount(null);
                                        }

                                        if (cell9.getType() != CellType.EMPTY){
                                            credreg.setTurnoverDebAmountCur(cell9.asNumber().longValue());
                                        } else if (cell9.getType() == CellType.EMPTY){
                                            credreg.setTurnoverDebAmountCur(null);
                                        }

                                        if (cell10.getType() != CellType.EMPTY){
                                            credreg.setRemnsDebCurrentVal(cell10.asNumber().doubleValue());
                                        } else if (cell10.getType() == CellType.EMPTY){
                                            credreg.setRemnsDebCurrentVal(null);
                                        }

                                        System.out.println("$$$$ ROW #" + row.getRowNum() + " IS FINISHED $$$");

                                        batch.add(credreg);

                                        if (batch.size() == 5000) {
                                            dataManager.save(batch);
                                            batch.clear();
                                        }
                                    });
                            if (!batch.isEmpty()) {
                                dataManager.save(batch);
                            }
                        }
                    }
                }
            } catch (IOException e) {
                notifications.create(Notifications.NotificationType.ERROR)
                        .withCaption(messages.getMessage(e.getMessage()))
                        .show();
            }
        } else {
            notifications.create(Notifications.NotificationType.ERROR)
                    .withCaption(messages.getMessage("ФАЙЛ НЕ ЗАГРУЖЕН"))
                    .show();
        }
    }
}

Caused by: java.lang.ClassCastException: class java.lang.String cannot be cast to class java.sql.Clob (java.lang.String is in module java.base of loader 'bootstrap'; java.sql.Clob is in module java.sql of loader 'platform')

Caused by: java.lang.IllegalStateException: Unsupported entity type class java.util.ArrayList
