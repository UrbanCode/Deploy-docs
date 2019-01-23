#  IBM z/OS agent user accounts

If you run the agent from a UNIX™ command line, the agent user account is the account that you use to log in to the UNIX shell. If you run the agent as a started task, the agent user account is assigned by the Resource Access Control Facility \(RACF®\) using the started procedures table \(ICHRIN03\) or the STARTED class. To learn more about RACF, see the *z/OS® Security Server RACF System Programmer's Guide, SA23-2287-00*.

The agent user account must have the following:

-   Access to the Time Sharing Option \(TSO\) and Interactive System Productivity Facility \(ISPF\) environments.
-   The ability to create temporary data sets. By default, HCL® UrbanCode™ Deploy uses the data-set prefix that is stored in the TSO profile. Otherwise, HCL UrbanCode Deploy uses the user ID as a temporary data-set prefix. You can specify a different prefix by setting the BUZ\_TMP\_DSN\_PREFIX environment variable in agent\_install\_dir/bin/setenv-zos.sh.
-   Sufficient virtual memory to run Java™ in the OMVS address space is required. The amount of required memory can vary based on which plug-ins are used in deployment processes. The following list includes typical values for RACF configuration parameters that specify virtual memory.
    -   ASSIZEMAX= 2147483647
    -   FILEPROCMAX= 00524287
    -   PROCUSERMAX= 00032767
    -   THREADSMAX= 00100000
-   Sufficient virtual storage limits, if the agent is running as a started task. To set the virtual storage limits, specify the REGION=0M parameter in the EXEC PGM=BPXBATCH statement.
-   A protected ID \(which can not be used to log in\) can be used as the agent ID. Because of the limitation of protected IDs, the ID cannot be used in steps that require a password or password phrase, for example, the Submit Job step or the CICS TS plug-in steps.
-   It is preferable for the installing ID to have read access to the BP.FILEATTR.APF resource in the FACILITY class profile to run the checkaccess command.

    **Note:** If read access is not granted, the following message might be displayed.

    ```
    chattr() error: rv=-1, errno=8B, rsn=0924041A
    ```

    Respond to this message with the following command that must be run immediately after the installation by an ID that has this access.

    extattr +a < agent dir\>/auth/checkaccess


**Parent topic:** [Security requirements on IBM z/OS computers](../../com.ibm.udeploy.admin.doc/topics/security_zos.md)

