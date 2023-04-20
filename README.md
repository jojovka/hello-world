# hello-world
Just my first repository

DataGrid.ButtonRenderer<PlannedWork> gridButtonRendererButtonFinish =
                getApplicationContext().getBean(DataGrid.ButtonRenderer.class);
        gridButtonRendererButtonFinish.setRendererClickListener(
                clickableRendererClickEvent -> {
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
                        if(lateStartFlag.get() == flagCheck.get() || lateEndFlag.get() == flagCheck.get()){
                            screenBuilders.editor(PlannedWork.class, this)
                                    .editEntity(plannedWorksDc.getItem(plannedWorkEndItem.getId()))
                                    .withOpenMode(OpenMode.DIALOG)
                                    .build()
                                    .show();
                        }
                        int versionWithComment = clickableRendererClickEvent.getItem().getVersion();
                        plannedWorksDc.getItem(plannedWorkEndItem.getId()).setVersion(versionWithComment);//Обновление optimistic lock
                        plannedWorkService.setFinishedPlannedWorkToReport(plannedWorksDc.getItem(plannedWorkEndItem.getId()));
                        plannedWorksDl.load();
                        plannedWorksTable.repaint();
                    } else {
                        notifications.create()
                                .withCaption("Невозможно завершить выполнение плановой работы")
                                .withDescription("Работа не была начата или уже завершена")
                                .show();
                    }
                });
        this.plannedWorksTable.getColumn("btnFinish")
                .setRenderer(gridButtonRendererButtonFinish);
