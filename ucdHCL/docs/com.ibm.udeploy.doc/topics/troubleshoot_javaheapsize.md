---
keyword: [troubleshoot, Java heap memory size]
---

# Determining the Java heap memory size

The Java heap is memory that contains objects used by Java programs. It contains objects that are currently in use, objects that are no longer needed, and free memory. Objects that are no longer needed are freed by the garbage collection process. The JVM heap size determines how often to run garbage collection and how long the garbage collection runs.

Tuning the heap size minimizes the amount of garbage collection processing. Insufficient Java heap space can result in out of memory errors or slow performance.

The JVM settings are specified in the set\_env file which is in the ucd-server/bin directory. The **JAVA\_OPTS** environment variable contains the following arguments related to heap size:

-   **-Xms**

    Initial Java heap size.

-   **-Xmx**

    Maximum Java heap size


**Parent topic:** [Logging](../topics/log_ov.md)

