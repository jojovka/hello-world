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
                                            credreg.setOperationDate(cell1.asDate());
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
                                            credreg.setTurnoverIntAmount(cell6.asNumber().doubleValue());
                                        } else if (cell6 == null){
                                            credreg.setTurnoverIntAmount(null);
                                        }

                                        if (cell7 != null){
                                            credreg.setTurnoverIntAmountCur(cell7.asNumber().doubleValue());
                                        } else if (cell7 == null){
                                            credreg.setTurnoverIntAmountCur(null);
                                        }

                                        if (cell8 != null){
                                            credreg.setTurnoverDebAmount(cell8.asNumber().longValue());
                                        } else if (cell8 == null){
                                            credreg.setTurnoverDebAmount(null);
                                        }

                                        if (cell9 != null){
                                            credreg.setTurnoverDebAmountCur(cell9.asNumber().longValue());
                                        } else if (cell9 == null){
                                            credreg.setTurnoverDebAmountCur(null);
                                        }

                                        if (cell10 != null){
                                            credreg.setRemnsDebCurrentVal(cell10.asNumber().doubleValue());
                                        } else if (cell10 == null){
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
