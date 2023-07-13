# hello-world
Just my first repository

io.jmix.reports.exception.ReportingException: An error occurred while saving result report. Template name [Корректировка кредитного регистра.xlsx] Report name [test_Корр-ка КР]
Failed to add parts from relationships of /
Failed to add parts from relationships of /xl/workbook.xml
Problem saving part /xl/worksheets/sheet1.xml
Error marshalling JaxbXmlPart /xl/worksheets/sheet1.xml
xl/worksheets/sheet1.xml's size exceeds the limit of 4GByte.
	at io.jmix.reports.runner.impl.ReportRunnerImpl.createReportDocumentInternal(ReportRunnerImpl.java:169)
	at io.jmix.reports.runner.impl.ReportRunnerImpl.run(ReportRunnerImpl.java:96)
	at io.jmix.reportsui.runner.impl.UiReportRunnerImpl$2.run(UiReportRunnerImpl.java:188)
	at io.jmix.reportsui.runner.impl.UiReportRunnerImpl$2.run(UiReportRunnerImpl.java:182)
	at io.jmix.ui.executor.LocalizedTaskWrapper.run(LocalizedTaskWrapper.java:54)
	at io.jmix.ui.executor.impl.WebBackgroundWorker$WebTaskExecutor.call(WebBackgroundWorker.java:206)
	at java.base/java.util.concurrent.FutureTask.run(FutureTask.java:264)
	at io.jmix.ui.executor.impl.WebBackgroundWorker$WebTaskExecutor.lambda$startExecution$1(WebBackgroundWorker.java:385)
	at java.base/java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1128)
	at java.base/java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:628)
	at java.base/java.lang.Thread.run(Thread.java:829)
