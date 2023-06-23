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
                        List<Credreg> entities = new ArrayList<>();
                        rows.forEach(row -> {
                            Credreg credreg = metadata.create(Credreg.class);
                            row.forEach(cell -> {
                                String columnName = cell.getColumnName();
                                Object value = cell.getValue();
                                // Check if value is not null or empty string
                                if (value != null && !value.toString().isEmpty()) {
                                    credreg.setValue(columnName, value);
                                }
                            });
                            entities.add(credreg);
                            // Commit every 1000 entities to optimize performance
                            if (entities.size() >= 1000) {
                                dataManager.commit(new CommitContext(entities));
                                entities.clear();
                            }
                        });
                        // Commit remaining entities
                        if (!entities.isEmpty()) {
                            dataManager.commit(new CommitContext(entities));
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
