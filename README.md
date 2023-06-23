# hello-world
Just my first repository

@Subscribe("attachmentFileField")
public void onAttachmentFileFieldFileUploadSucceed(SingleFileUploadField.FileUploadSucceedEvent event) {
    FileRef fileRef = attachmentFileField.getValue();
    if (fileRef != null) {
        try (InputStream is = fileStorage.openStream(fileRef)) {
            try (ReadableWorkbook wb = new ReadableWorkbook(is)) {
                Sheet sheet = wb.getFirstSheet();
                Map<Integer, String> fieldNames = new HashMap<>();
                try (Stream<Row> rows = sheet.openStream()) {
                    // Assuming the first row contains column names
                    Row headerRow = rows.iterator().next();
                    for (Cell cell : headerRow) {
                        fieldNames.put(cell.getColumnIndex(), cell.asString());
                    }
                    
                    List<Credreg> entities = new ArrayList<>();
                    rows.skip(1).forEach(row -> {  // Skip the header row
                        Credreg credreg = dataManager.create(Credreg.class);
                        row.forEach(cell -> {
                            int columnIndex = cell.getColumnIndex();
                            Object value = cell.getValue();
                            String fieldName = fieldNames.get(columnIndex);
                            if (fieldName != null && value != null && !value.toString().isEmpty()) {
                                credreg.setValue(fieldName, value);
                            }
                        });
                        entities.add(credreg);
                        if (entities.size() >= 1000) {
                            dataManager.commit(new CommitContext(entities));
                            entities.clear();
                        }
                    });
                    if (!entities.isEmpty()) {
                        dataManager.commit(new CommitContext(entities));
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
