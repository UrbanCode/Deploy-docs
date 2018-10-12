# Automatically downloading audit log files {#troubleshoot_logDownload .task}

You can automatically download audit log files at a regular interval, such as every day.

Before scheduling audit log downloads, manually download the audit log. Log entries that are made before the first scheduled download are not be written to the downloaded file.

You can speed up log cleanup by regularly downloading the audit log file. This feature works especially well with enable audit log cleanup enabled, **Settings \> System \> Audit Log \> Audit Log settings \> Enable Audit Log Cleanup** file. You can download the log files daily and then clean up the logs. See, [Server settings](../../com.ibm.udeploy.admin.doc/topics/settings_system.md).

You can schedule regular downloads by modifying the audit-log-to-file appenders in the log4j.properties file. The following code fragment illustrates how you might schedule downloads:

```
 log4j.appender.audit-log-to-file=org.apache.log4j.DailyRollingFileAppender
log4j.appender.audit-log-to-file.File=../var/log/audit.log
log4j.appender.audit-log-to-file.MaxFileSize=100MB
log4j.appender.audit-log-to-file.DatePattern='.'yyyy-MM-dd
log4j.appender.audit-log-to-file.layout=org.apache.log4j.PatternLayout
log4j.appender.audit-log-to-file.layout.ConversionPattern=%m%n
log4j.logger.AuditLog=DEBUG, audit-log-to-file
log4j.additivity.AuditLog=false
```

1.   Edit the log4j.properties file. Use a text editor to edit the file. You can also access the file by clicking **Settings** \> **Logging**. 
2.   Modify the audit-log-to-file appenders. 
3.   Restart the server. 

**Parent topic:** [Logging](../topics/log_ov.md)

