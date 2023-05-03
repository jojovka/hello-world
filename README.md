# hello-world
Just my first repository

Exception in thread "Timer-0" java.lang.IllegalStateException: Authentication is not set. Use SystemAuthenticator in non-user requests like schedulers or asynchronous calls.

Timer timer = new Timer();
        timer.schedule(new TimerTask() {
            @Override
            public void run() {
                log.info("Starting update UI...");
                plannedWorksDl.load();
                log.info("finished update UI");
            }
        }, 0, 60*1000);

Exception in thread "Timer-0" io.jmix.ui.executor.IllegalConcurrentAccessException: UI Shared state was accessed from a background thread

