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

                    AtomicInteger rowIndex = new AtomicInteger();
                    Row headerRow = null;
                    List<Credreg> credregs = new ArrayList<>();
                    int batchSize = 5000;

                    sheet.openStream().forEach(row -> {
                        if (rowIndex.getAndIncrement() == 0) {
                            headerRow = row; // Get the header row
                        } else {
                            Credreg credreg = dataManager.create(Credreg.class);
                            for (int i = 0; i < row.getCellCount(); i++) {
                                Cell cell = row.getCell(i);
                                String columnName = headerRow.getCell(i).getText().toString();
                                String methodName = "set" + CaseFormat.UPPER_UNDERSCORE.to(CaseFormat.UPPER_CAMEL, columnName);
                                Method method;
                                try {
                                    Object value;
                                    switch (cell.getType()) {
                                        case NUMBER:
                                            value = cell.asNumber().intValue();
                                            break;
                                        case BOOLEAN:
                                            value = cell.asBoolean();
                                            break;
                                        case STRING:
                                            String text = cell.toString();
                                            if ("IS_IMPAIRED".equals(columnName.toUpperCase())) {
                                                value = "ИСТИНА".equals(text);
                                            } else {
                                                value = text;
                                            }
                                            break;
                                        default:
                                            value = cell.getValue();
                                    }
                                    method = Credreg.class.getMethod(methodName, value.getClass());
                                    method.invoke(credreg, value);
                                } catch (NoSuchMethodException | IllegalAccessException | InvocationTargetException e) {
                                    notifications.create(Notifications.NotificationType.ERROR)
                                            .withCaption(e.getMessage())
                                            .show();
                                }
                            }
                            credregs.add(credreg);

                            // If we've reached batch size or this is the last row, save the data
                            if (credregs.size() == batchSize || !sheet.openStream().iterator().hasNext()) {
                                dataManager.save(credregs);
                                credregs.clear();
                            }
                        }
                    });
                }
            }
        }
