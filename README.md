# hello-world
Just my first repository

DevelopmentException: Target kz.eub.moncl.screen.plannedwork.PlannedWorkBrowse does not support event type class kz.eub.moncl.app.dataUpdater.DataUpdatedEvent

Caused by: org.springframework.beans.factory.support.ScopeNotActiveException: Error creating bean with name 'ui_Screens': Scope 'vaadin-ui' is not active for the current thread; consider defining a scoped proxy for this bean if you intend to refer to it from a singleton; nested exception is java.lang.IllegalStateException: No VaadinSession bound to current thread

NoUniqueBeanDefinitionException: No qualifying bean of type 'org.springframework.core.task.TaskExecutor' available: expected single matching bean but found 4: applicationTaskExecutor,core_ThreadPoolTaskScheduler,ui_ThreadPoolTaskScheduler,mailSendTaskExecutor

Exception in thread "task-1" java.lang.IllegalStateException: Authentication is not set. Use SystemAuthenticator in non-user requests like schedulers or asynchronous calls.

Exception in thread "task-1" io.jmix.ui.executor.IllegalConcurrentAccessException: UI Shared state was accessed from a background thread

Timer timer = new Timer();
        timer.schedule(new TimerTask() {
            @Override
            public void run() {
                log.info("Starting update UI...");
                plannedWorksDl.load();
                log.info("finished update UI");
            }
        }, 0, 60*1000);

