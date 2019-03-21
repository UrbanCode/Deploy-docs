# Troubleshooting problems on z/OS

To troubleshoot problems on agent computers that are running IBM® z/OS®, examine the agent log files.

## Agent log files

Agent log files are stored in the UTF-8 format. To read agent log files, use an editor that supports the UTF-8 format. For example, use IBM Rational® Developer for z Systems™ or the z/OS UNIX™ Directory List Utility.

Alternately, convert the agent log files to a different format. To convert an agent log file to EBCDIC IBM-1047 encoding, type the following text at a command line:

```
iconv -f utf8 -t ibm1047 agent.out > agent.out.1047
```

## Common problems

-   **Out of memory errors**

    If the agent does not start or the deployment tools do not run, and a message similar to the following message is displayed on the console or written to the agent/var/log/stdout log file, the OMVS segment is not in the user profile or the memory that is assigned to the user account is not sufficient for the OMVS segment.

    ```
    JVMJ9VM015W Initialization error for library j9jit24(11): cannot initialize JIT.
    Could not create the Java virtual machine.
    <JIT: fatal error, failed to allocate 8192 Kb data cache>
    ```

    To correct the problem, ensure that the agent user account meets the security requirements. To learn more, see [Security requirements on IBM z/OS computers](../../com.udeploy.admin.doc/topics/security_zos.md).

-   **ISPF gateway is not configured correctly**

    The error message The ISPF gateway is not configured correctly is typically followed by an XML response that indicates the specific problem. Typical problems include the following issues:

    -   The user account does not have write access to the ispf\_log\_directory/WORKAREA directory.
    -   The user account does not have an ISPF profile.
    -   The ISPF gateway cannot allocate the data sets defined in the ISPF.conf file. By default, the ISPF.conf file is in the agent/conf/toolkit/ directory.
-   **EDC5112I Response temporarily unavailable**

    The error message EDC5112I Response temporarily unavailable is displayed when no z/OS® UNIX™ processes are available to run the ISPF client gateway. To work around this behavior, set the PROCUSERMAX parameter in the OMVS segment of the user account Resource Access Control Facility profile to the value specified in the security requirements. To learn more, see [Security requirements on IBM z/OS computers](../../com.udeploy.admin.doc/topics/security_zos.md).

-   **ISPF.SYSTSPRT error: EDC5129I No such file or directory.**

    The name of the ISPF client gateway log directory must be shorter than 51 bytes. If a directory with longer name is used, you will see the following errors when using the TSO/ISPF command plug-in step or creating a component version.

    ```
    *** fopen() error for
    ispf_log_directory/WORKAREA/WORKAREA/UCDUSER.ID00xxxx.ISPF.SYSTSPRT error: EDC5129I No such file or
    directory.
    ```

    ```
    Bad call : cp: ispf_log_directory/WORKAREA/UCDUSER.ID00xxxx.ISPF.SYSTSPRT: EDC5129I No such file or
    directory.
    ```

    To correct the problem, use a log directory which is shorter than 51 bytes. You can do this by reinstalling the agent and toolkit or by modifying the directory in the following two configuration files:

    -   agent\_dir/conf/toolkit/ISPZXENV
    -   agent\_dir/conf/toolkit/installed.properties

**Parent topic:** [z/OS considerations for UrbanCode Deploy](../topics/zos_ch.md)

