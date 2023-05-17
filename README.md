# hello-world
Just my first repository

@Install(to = "plannedWorksTable", subject = "rowStyleProvider")
    private String styledGridRowStyleProvider(PlannedWork plannedWork) {
        if (LocalDateTime.now().isAfter(plannedWork.getScheduledStartDateTime().minusMinutes(10)) && LocalDateTime.now().isBefore(plannedWork.getScheduledStartDateTime())) {
            return "ten-minutes";
        } else if (LocalDateTime.now().isAfter(plannedWork.getScheduledEndDateTime())) {
            return "late";
        }else if (LocalDateTime.now().isAfter(plannedWork.getScheduledStartDateTime()) && LocalDateTime.now().isBefore(plannedWork.getScheduledEndDateTime())) {
            return "started";
        }
        return null;
    }
