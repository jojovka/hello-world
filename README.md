# hello-world
Just my first repository

@Override
    public void saveObjectsListUsingSaveContext(List<?> objects) {
        SaveContext saveContext = new SaveContext().setDiscardSaved(true);
        for (int i = 0; i < objects.size(); i++) {
            saveContext.saving(objects.get(i));
            if (i > 0 && (i % 100 == 0 || i == objects.size() - 1)) {
                dataManager.save(saveContext);
                saveContext = new SaveContext().setDiscardSaved(true);
            }
        }
        System.out.println("()()()()()()()()SAVED BATCH()()()()()()()()");
    }
