# Logging {#log_ov .concept}

The server maintains logs for auditing and troubleshooting.

## Audit log { .section}

The audit log shows information about who accessed the server and what changes each user made.

## Diagnostics log { .section}

The diagnostics log shows a table of information about actions on the server. This table shows which user ran an action, when that action was run and what part of the server API was used.

## Server output log { .section}

The server output log shows information about all the actions that are performed on the server.

-   **[Viewing logs](../topics/log_audit.md)**  
You can view logs from the **Settings** \> **System** page.
-   **[Changing the server output log contents](../topics/log_log4j.md)**  
The server stores its log by using Apache Log4j version 1.2.16. You can edit the Log4j settings to change the format of the log and the information that is added to the log.
-   **[Automatically downloading audit log files](../topics/troubleshoot_logDownload.md)**  
You can automatically download audit log files at a regular interval, such as every day.
-   **[Increasing the size of the log file](../topics/troubleshoot_logsize.md)**  
Log data contains information that is written by components within the product. The log provides a snapshot of the flow and transfer of information between components. The log data includes the time frames for when problem occurred on the server, client, and agent. Because the log file holds a limited amount of data, data related to a problem can be overwritten.
-   **[Determining the Java heap memory size](../topics/troubleshoot_javaheapsize.md)**  
The Java heap is memory that contains objects used by Java programs. It contains objects that are currently in use, objects that are no longer needed, and free memory. Objects that are no longer needed are freed by the garbage collection process. The JVM heap size determines how often to run garbage collection and how long the garbage collection runs.

**Parent topic:** [Troubleshooting and support](../topics/c_node_troubleshooting.md)

