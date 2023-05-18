# hello-world
Just my first repository

@Install(to = "plannedWorksTable", subject = "rowStyleProvider")
    private String styledGridRowStyleProvider(PlannedWork plannedWork) {
        if (LocalDateTime.now().isAfter(plannedWork.getScheduledStartDateTime().minusMinutes(10)) && LocalDateTime.now().isBefore(plannedWork.getScheduledStartDateTime())) {
            return "ten-minutes";
        } else if (LocalDateTime.now().isAfter(plannedWork.getScheduledEndDateTime())) {
            plannedWorkService.setCounterFlagFalse(plannedWork);
            return "late";
        }else if (LocalDateTime.now().isAfter(plannedWork.getScheduledStartDateTime()) && LocalDateTime.now().isBefore(plannedWork.getScheduledEndDateTime())) {
            plannedWorkService.setCounterFlagTrue(plannedWork);
            return "started";
        }
        return null;
    }

public void setCounterFlagTrue(PlannedWork plannedWork){
        plannedWork.setCounted(true);
        int versionWithComment = plannedWork.getVersion();
        plannedWork.setVersion(versionWithComment);
        dataManager.save(plannedWork);
    }
    public void setCounterFlagFalse(PlannedWork plannedWork){
        plannedWork.setCounted(false);
        int versionWithComment = plannedWork.getVersion();
        plannedWork.setVersion(versionWithComment);
        dataManager.save(plannedWork);
    }
