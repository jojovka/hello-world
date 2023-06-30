# hello-world
Just my first repository

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
                            int counter = 1;
                            rows.skip(1)
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

                                        if (cell0 != null){
                                            credreg.setSourceSystem(cell0.asString());
                                        } else if (cell0 == null) {
                                            credreg.setSourceSystem("");
                                        }

                                        if (cell1 != null){
                                            credreg.setOperationDate(new Date(cell1.asString()));
                                        } else if (cell1 == null) {
                                            credreg.setOperationDate(null);
                                        }

                                        if (cell2 != null){
                                            credreg.setPrimaryContractNo(cell2.asString());
                                        } else if (cell2 == null) {
                                            credreg.setPrimaryContractNo("");
                                        }

                                        if (cell5 != null){
                                            credreg.setContractS(cell5.asNumber().longValue());
                                        }else if (cell5 == null) {
                                            credreg.setContractS(null);
                                        }

                                        if (cell6 != null){
                                            credreg.setOperationDate(new Date(cell6.asString()));
                                        } else if (cell6 == null){
                                            credreg.setOperationDate(null);
                                        }

                                        if (cell7 != null){
                                            credreg.setTurnoverIntAmount(cell7.asNumber().doubleValue());
                                        } else if (cell7 == null){
                                            credreg.setTurnoverIntAmount(null);
                                        }

                                        if (cell8 != null){
                                            credreg.setTurnoverIntAmountCur(cell8.asNumber().doubleValue());
                                        } else if (cell8 == null){
                                            credreg.setTurnoverIntAmountCur(null);
                                        }

                                        if (cell9 != null){
                                            credreg.setTurnoverDebAmount(cell9.asNumber().longValue());
                                        } else if (cell9 == null){
                                            credreg.setTurnoverDebAmount(null);
                                        }

                                        if (cell10 != null){
                                            credreg.setTurnoverDebAmountCur(cell10.asNumber().longValue());
                                        } else if (cell10 == null){
                                            credreg.setTurnoverDebAmountCur(null);
                                        }


                                        batch.add(credreg);

                                        if (batch.size() == 5000) {
                                            batch.forEach(entity -> dataManager.save(entity));
                                            batch.clear();
                                        }
                                    });
                            if (!batch.isEmpty()) {
                                batch.forEach(entity -> dataManager.save(entity));
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
    }

at kz.eub.report360.screen.credreg.CredregBrowse.lambda$onAttachmentFileFieldFileUploadSucceed$0
