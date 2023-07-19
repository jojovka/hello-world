# hello-world
Just my first repository

@Subscribe("attachmentFileField")
    public void onAttachmentFileFieldFileUploadSucceed(SingleFileUploadField.FileUploadSucceedEvent event) {
        SaveContext saveContext = new SaveContext().setDiscardSaved(true);
        FileRef fileRef = attachmentFileField.getValue();
        if (fileRef != null) {
            try {
                try (InputStream is = fileStorage.openStream(fileRef)) {
                    try (ReadableWorkbook wb = new ReadableWorkbook(is)) {
                        Sheet sheet = wb.getFirstSheet();
                        try (Stream<Row> rows = sheet.openStream()) {
                            List<Credreg> batch = new ArrayList<>(10000);
                            LocalDateTime localDateTimeStart = LocalDateTime.now();
                            rows.skip(2)
                                    .forEach(row -> {
                                        Credreg credreg = dataManager.create(Credreg.class);
                                        CredregCompKey credregCompKey = dataManager.create(CredregCompKey.class);

                                        Cell cell0 = row.getCell(0);
                                        Cell cell1 = row.getCell(1);
                                        Cell cell2 = row.getCell(2);
                                        Cell cell3 = row.getCell(3);
                                        Cell cell4 = row.getCell(4);
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

                                        if (cell3.getType() != CellType.EMPTY){
                                            credregCompKey.setEfBatchesInt(cell3.asNumber().longValue());
                                        } else if (cell3.getType() == CellType.EMPTY) {
                                            credregCompKey.setEfBatchesInt(null);
                                        }

                                        if (cell4.getType() != CellType.EMPTY){
                                            credregCompKey.setEfContract(cell4.asNumber().longValue());
                                        } else if (cell4.getType() == CellType.EMPTY) {
                                            credregCompKey.setEfBatchesInt(null);
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

                                        credreg.setId(credregCompKey);
                                        batch.add(credreg);

                                        if (batch.size() == 10000) {
                                            saveObjectsListUsingSaveContext(batch);
                                            batch.clear();
                                        }
                                    });
                            if (!batch.isEmpty()) {
                                saveObjectsListUsingSaveContext(batch);
                                batch.clear();
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

@Override
    public void saveObjectsListUsingSaveContext(List<?> objects) {
        SaveContext saveContext = new SaveContext().setDiscardSaved(true);
        for (int i = 0; i < objects.size(); i++) {
            saveContext.saving(objects.get(i));
            if (i > 0 && (i % 50 == 0 || i == objects.size() - 1)) {
                dataManager.save(saveContext);
                saveContext = new SaveContext().setDiscardSaved(true);
                System.out.println("()()()()()()()()SAVED BATCH 50()()()()()()()()");
            }
        }
    }
