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
                        // Получить первую строку (заголовки столбцов)
                        Row header = rows.iterator().next();

                        // Пройти по каждой строке данных
                        rows.forEach(dataRow -> {
                            Credreg credreg = dataManager.create(Credreg.class); // Создать новый экземпляр Credreg
                            for (int i = 0; i < dataRow.getCellCount(); i++) {
                                String columnName = header.getCell(i).asString();
                                String methodName = "set" + columnName.substring(0, 1).toUpperCase() + columnName.substring(1);
                                try {
                                    Method method = Credreg.class.getMethod(methodName, String.class); // Предполагается, что все поля - строки
                                    method.invoke(credreg, dataRow.getCell(i).asString()); // Задать значение поля
                                } catch (NoSuchMethodException | IllegalAccessException | InvocationTargetException e) {
                                    // Обработка исключений
                                }
                            }
                            dataManager.commit(credreg); // Сохранить Credreg
                        });
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
