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
                            // Row 0 usually contains the column names, skip it
                            rows.skip(1).forEach(row -> {
                                Credreg credreg = dataManager.create(Credreg.class);
                                for (int i = 0; i < row.getCellCount(); i++) {
                                    Cell cell = row.getCell(i);
                                    String columnName = sheet.range(0, i).value().toString();
                                    String methodName = "set" + capitalize(columnName);
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
                                                .withCaption(messages.getMessage(e.getMessage()))
                                                .show();
                                    }
                                }
                                credregs.add(credreg);
                            });
                            CommitContext commitContext = new CommitContext(credregs);
                            dataManager.commit(commitContext);
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

    public static String capitalize(String str){
        if(str == null || str.isEmpty()){
            return str;
        }

        return str.substring(0, 1).toUpperCase() + str.substring(1);
    }






