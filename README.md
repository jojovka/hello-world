# hello-world
Just my first repository

User user = usersTable.getSingleSelected();
        RoleAssignmentEntity roleAssignment = dataManager.create(RoleAssignmentEntity.class);
        if (user != null) {
            boolean hasRole = dataManager.load(RoleAssignmentEntity.class)
                    .query("select r from sec_RoleAssignmentEntity r where r.username = :username and r.roleCode = :roleCode")
                    .parameter("username", user.getUsername())
                    .parameter("roleCode", "manager")
                    .optional()
                    .isPresent();
            if (!hasRole) {
                roleAssignment.setUsername(user.getUsername());
                roleAssignment.setRoleCode("manager");
                roleAssignment.setRoleType(RoleAssignmentRoleType.RESOURCE);
                dataManager.save(roleAssignment);
                notifications.create(Notifications.NotificationType.WARNING)
                        .withCaption("Пользователю присвоена роль Менеджера")
                        .show();
            } else {
                notifications.create(Notifications.NotificationType.ERROR)
                        .withCaption("Ошибка")
                        .withDescription("Пользователь уже имеет роль Менеджера")
                        .show();
            }
        }

