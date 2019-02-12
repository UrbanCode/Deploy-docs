# Increasing the amount of memory that is available to the server

If you see "Out of memory" errors or are using the server at high capacity, increase the amount of system memory that is available to the server.

For servers that are running as a service on Windows™, see the following technote: [http://www-01.ibm.com/support/docview.wss?uid=swg21698228](http://www-01.ibm.com/support/docview.wss?uid=swg21698228).

1.  To increase the memory for the server on Windows for a non-service installation, or on Linux™ or UNIX™ systems, follow these steps:
2.   Stop the server. 
3.   In the bin/set\_env.cmd file \(Windows\) or bin/set\_env file \(Linux and UNIX\), increase the memory in the `JAVA_OPTS` parameter. For example, the current file might have a line that begins with the following code:

    ```
    JAVA_OPTS="-Xmx2048m
    ```

    To increase the memory, change the parameter that begins with the code `-Xmx`. For example, to increase the memory to 4 GB, use the following value: `-Xmx4096m`. Be sure to include the "`m`" at the end of the parameter.

4.   Save the file and restart the server. 

**Parent topic:** [Server settings and configuration](../topics/settings_ch.md)

