# hello-world
Just my first repository

screenBuilders.editor(PlannedWork.class, this)
                                    .editEntity(plannedWorksDc.getItem(plannedWorkEndItem.getId()))
                                    .withOpenMode(OpenMode.DIALOG)
                                    .build()
                                    .addAfterCloseListener(afterCloseEvent -> {
                                        int versionWithComment = clickableRendererClickEvent.getItem().getVersion();
                                        plannedWorksDc.getItem(plannedWorkEndItem.getId()).setVersion(versionWithComment);//Обновление optimistic lock
                                        plannedWorkService.setFinishedPlannedWorkToReport(plannedWorksDc.getItem(plannedWorkEndItem.getId()));
                                        plannedWorksDl.load();
                                        plannedWorksTable.repaint();
                                        });
                                    .show();
