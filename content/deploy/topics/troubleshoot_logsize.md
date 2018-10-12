# Increasing the size of the log file {#troubleshoot_logsize .task}

Log data contains information that is written by components within the product. The log provides a snapshot of the flow and transfer of information between components. The log data includes the time frames for when problem occurred on the server, client, and agent. Because the log file holds a limited amount of data, data related to a problem can be overwritten.

The server and agent store log data by using Apache Log4j. Settings for Log4j logging are in the log4j.properties file, which resides on both the server and agent. This file contains multiple sections for different purposes defining Log4j appenders. Some sections are enabled by default, such as the server file appender and cleanup appender. Other sections are disabled by default, such as the server audit logging and SSL appender. When you report a problem to IBM Software Support, the support specialist will guide you through which sections to enable.

You can edit the Log4j settings to avoid losing relevant data because the log file is overwritten too soon. Setting for Log4j are in the log4j.properties on the IBM® UrbanCode® Deploy server and agent.

-   For the server, this file is in the server/appdata/conf/server/ directory.
-   For the agent, this file is in the agent/conf/agent/ directory.

The **MaxBackupIndex** parameter specifies how many backup log files are maintained beyond the current log file. The default value is two. An IBM support specialist can help determine the appropriate value to specify.

When you increase the number of log files more disk space is needed. In the following code example, the size of each file is 50 MB. The disk space that is needed for additional files is \(MaxBackupIndex\_value \* 50MB\) + size of current log file.

```
 log4j.appender.file=org.apache.log4j.RollingFileAppender 
log4j.appender.file.File=../var/log/deployserver.out 
log4j.appender.file.MaxFileSize=50MB 
log4j.appender.file.MaxBackupIndex=2
```

1.   Edit the log4j.properties file. Use a text editor to edit the file. For the server, you can also access the file by clicking**Settings** \> **Logging**. 
2.   Change the value of the **MaxBackupIndex** parameter. 
3.   Restart the server. 

**Parent topic:** [Logging](../topics/log_ov.md)

