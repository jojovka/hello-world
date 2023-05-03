# hello-world
Just my first repository

DevelopmentException: Target kz.eub.moncl.screen.plannedwork.PlannedWorkBrowse does not support event type class kz.eub.moncl.app.dataUpdater.DataUpdatedEvent

Caused by: org.springframework.beans.factory.support.ScopeNotActiveException: Error creating bean with name 'ui_Screens': Scope 'vaadin-ui' is not active for the current thread; consider defining a scoped proxy for this bean if you intend to refer to it from a singleton; nested exception is java.lang.IllegalStateException: No VaadinSession bound to current thread

NoUniqueBeanDefinitionException: No qualifying bean of type 'org.springframework.core.task.TaskExecutor' available: expected single matching bean but found 4: applicationTaskExecutor,core_ThreadPoolTaskScheduler,ui_ThreadPoolTaskScheduler,mailSendTaskExecutor
