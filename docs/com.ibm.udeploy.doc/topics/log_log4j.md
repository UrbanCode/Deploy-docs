# Changing the server output log contents

The server stores its log by using Apache Log4j version 1.2.16. You can edit the Log4j settings to change the format of the log and the information that is added to the log.

The Log4j logging settings are stored in the file app\_data/conf/server/log4j.properties, where app\_data is the application data folder. You can edit this file directly on the server or open it by clicking **Settings** \> **Logging**.

**Note:** Do not change the name and location of the server log. If the location of the deployserver.out file is changed in log4j.properties, you will not be able to view or download the server log file from the user interface.

For example, to log all REST calls that are made to the server, uncomment the following lines of code at the bottom of the file:

```
log4j.appender.audit=org.apache.log4j.RollingFileAppender
log4j.appender.audit.File=../var/log/user_audit.log
log4j.appender.audit.MaxFileSize=10MB
log4j.appender.audit.MaxBackupIndex=5
log4j.appender.audit.layout=org.apache.log4j.PatternLayout
log4j.appender.audit.layout.ConversionPattern=%d{ISO8601} - %m%n

log4j.additivity.com.urbancode.ds.web.filter.LoggingFilter=false
log4j.logger.com.urbancode.ds.web.filter.LoggingFilter=DEBUG, audit
```

Now, all REST calls are stored in the file server/var/log/user\_audit.log, as in the following example:

```
2015-08-05 11:20:23,882 - User admin from host 127.0.0.1
accessing: GET @ /rest/deploy/environment
2015-08-05 11:20:24,009 - User admin from host 127.0.0.1
accessing: POST @ /rest/deploy/environment/compliancies
```

To log authentication failures, add the following line of code to the log4j.properties file:

```
log4j.logger.com.urbancode.security.persistence.hibernate.HibernateUserFactory=TRACE
```

For more information on Log4j, see [http://logging.apache.org/log4j/1.2/](http://logging.apache.org/log4j/1.2/).

**Parent topic:** [Logging](../topics/log_ov.md)

