# hello-world
Just my first repository

try {
        String filePath = event.getFilePath();
        
        try (InputStream is = new FileInputStream(filePath);
             Reader reader = new Reader(is)) {
                
            for (ReadableSheet sheet : reader) {
                for (Row row : sheet) {
                    CredReg credReg = dataManager.create(CredReg.class);
                    
                    for (int i = 0; i < row.getCellCount(); i++) {
                        Cell cell = row.getCell(i);
                        
                        // Получаем имя столбца из файла Excel
                        String columnName = sheet.getCell(i, 0).getText();
                        
                        // Преобразуем имя столбца в имя метода set (например, для столбца "field1" метод будет "setField1")
                        String methodName = "set" + columnName.substring(0, 1).toUpperCase() + columnName.substring(1);
                        
                        // Получаем класс, чтобы найти нужный метод
                        Class<?> clazz = credReg.getClass();
                        
                        // Ищем метод с нужным именем и типом параметра
                        Method method = clazz.getMethod(methodName, String.class);
                        
                        // Вызываем метод для текущей сущности, передавая значение ячейки в качестве параметра
                        method.invoke(credReg, cell.getText());
                    }
                    
                    dataManager.save(credReg);
                }
            }
        }
    } catch (IOException | NoSuchMethodException | IllegalAccessException | InvocationTargetException e) {
        throw new RuntimeException("Ошибка при чтении файла Excel", e);
    }
