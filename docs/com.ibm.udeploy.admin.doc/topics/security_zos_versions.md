#  IBM z/OS component versions

Component versions forIBM® z/OS® are imported from the build LPAR by using the buzltool.sh command.

**Note:** The user account that runs buztool.sh must have access to the UNIX™ directories and files and MVS™ data sets. Refer to [IBM z/OS directories and data sets](security_zos_files.md).

The user account used to import versions must have the following:

-   Access to the Time Sharing Option \(TSO\) and Interactive System Productivity Facility \(ISPF\) environments
-   Sufficient virtual memory to run Java™ in the OMVS address space. A minimum of 200 MB of virtual memory is required. The following list includes typical values for RACF® configuration parameters that specify virtual memory:
    -   ASSIZEMAX= 2147483647
    -   FILEPROCMAX= 00524287
    -   PROCUSERMAX= 00032767
    -   THREADSMAX= 00100000

**Parent topic:** [Security requirements on IBM z/OS computers](../../com.ibm.udeploy.admin.doc/topics/security_zos.md)

