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
                            List<Credreg> credregs = new ArrayList<>();
                            Row headerRow = rows.iterator().next();
                            rows.skip(1).forEach(row -> {
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
                            });
                            int batchSize = 5000;
                            List<Credreg> batch = new ArrayList<>(batchSize);
                            for (int i = 0; i < credregs.size(); i++) {
                                batch.add(credregs.get(i));
                                if ((i + 1) % batchSize == 0 || (i + 1) == credregs.size()) {
                                    dataManager.save(batch);
                                    batch.clear();
                                }
                            }
                        }
                    }
                }
            } catch (IOException e) {
                notifications.create(Notifications.NotificationType.ERROR)
                        .withCaption(e.getMessage())
                        .show();
            }
        } else {
            notifications.create(Notifications.NotificationType.ERROR)
                    .withCaption("ФАЙЛ НЕ ЗАГРУЖЕН")
                    .show();
        }
    }
