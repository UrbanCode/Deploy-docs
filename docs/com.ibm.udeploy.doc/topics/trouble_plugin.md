# Troubleshooting plug-ins

Use the following procedures and tips to help troubleshoot plug-ins that you use with HCL® UrbanCode™ Deploy:

[Installing a plug-in generates an error: Error loading plugin: undefined](#).

[Loading a plug-in generates errors and steps are not displayed in the process editor](#).

**Parent topic:** [Troubleshooting the HCL UrbanCode Deploy server and agents](../topics/trouble_serveragents_ov.md)

## Installing a plug-in generates an error: Error loading plugin: undefined

You attempt to install a plug-in, and you receive this message: Error loading plugin: undefined. This error message is displayed when the file system has insufficient space. The plug-in requires more space even though it seems as though enough space is available for installation.

1.   Depending on your hardware, add more space to the file system, and then try to install the plug-in again. 

## Loading a plug-in generates errors, and steps are not displayed in the process editor

You installed a trial version of HCL UrbanCode Deploy with IBM® DB2® as database. After starting the server, you cannot see any plug-ins and you are unable to load new plug-ins. Numerous errors are written to the log.

1.   The pagesize must be specified correctly when the DB2 database is created. HCL UrbanCode Deploy requires a pagesize of 32 k. See [Configuring a DB2 database for the HCL UrbanCode Deploy server](../../com.ibm.udeploy.install.doc/topics/dbinstall_db2.md). 

