# hello-world
Just my first repository

public class CredregExcelDataImporter implements ExcelDataImporter{
    @PersistenceContext
    EntityManager entityManager;
    @Autowired
    TransactionTemplate transactionTemplate;
    @Override
    public void saveObjectsList(List<?> objects) {
        transactionTemplate.executeWithoutResult(transactionStatus -> {
            int i = 0;
            for (Object object : objects){
                entityManager.persist(object);
            }
            entityManager.flush();
            entityManager.clear();
            System.out.println("()()()()()()()()SAVED BATCH()()()()()()()()");
        });
    }
}

public interface ExcelDataImporter {
    void saveObjectsList(List<?> objects);
}

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

                                        batch.add(credreg);

                                        if (batch.size() == 5000) {
                                            excelDataImporter.saveObjectsList(batch);
                                            batch.clear();
                                        }
                                    });
                            if (!batch.isEmpty()) {
                                excelDataImporter.saveObjectsList(batch);
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

Caused by: java.lang.IllegalArgumentException: Object: kz.eub.report360.entity.Credreg-kz.eub.report360.entity.key.CredregCompKey@3c1 [new] is not a known Entity type.
