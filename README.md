# hello-world
Just my first repository

@Subscribe("attachmentFileField")
public void onAttachmentFileFieldFileUploadSucceed(SingleFileUploadField.FileUploadSucceedEvent event) {
    FileRef fileRef = attachmentFileField.getValue();
    if (fileRef != null) {
        try (InputStream is = fileStorage.openStream(fileRef)) {
            try (Reader reader = new ReadableWorkbook(is)) {
                Sheet sheet = reader.getFirstSheet();
                try (Stream<Row> rows = sheet.openStream()) {
                    rows.forEach(row -> {
                        Credreg credreg = dataManager.create(Credreg.class);
                        for (Cell cell : row.getCells()) {
                            String columnName = cell.getColumnName(); // get column name
                            String setterMethodName = "set" + Character.toUpperCase(columnName.charAt(0)) + columnName.substring(1);
                            Method setterMethod;
                            try {
                                // get the setter method for this column
                                setterMethod = Credreg.class.getMethod(setterMethodName, cell.getData().getClass());
                                // invoke the setter method to set the value in your entity
                                setterMethod.invoke(credreg, cell.getData());
                            } catch (NoSuchMethodException | IllegalAccessException | InvocationTargetException e) {
                                notifications.create(Notifications.NotificationType.ERROR)
                                        .withCaption(messages.getMessage(e.getMessage()))
                                        .show();
                            }
                        }
                        dataManager.commit(credreg);
                    });
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
