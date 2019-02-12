# Deploying by using the Job Monitor

You use the Job Monitor to submit jobs and to monitor the job status in your deployment. You must ensure that you have a Job Monitor task running and that you run the Urban Code Deploy process to submit or to monitor the job. Then, you must set up Job Monitor connection properties in your HCL® UrbanCode™ Deploy environment.

Install the following agent or product and use the Job Monitor that is bundled with it:

-   z/OS agent
-   IBM Developer for IBM Z
-   IBM Rational Team Concert

**Note:** For the z/OS agent, the Job Monitor is installed automatically in the **hlq.SBUZAUTH** data set. Also, the LOOPBACK\_ONLY property must be set to OFF in the Job Monitor configuration file.

**Submitting and monitoring jobs in deployment processes**

1.  Start the Job Monitor task and check that a task that is called **JMON** is running.
2.  To submit or to monitor jobs, run the UrbanCode Deploy process that uses the Submit Job or Wait For Job steps.
3.  Set the following Job Monitor connection properties in the HCL UrbanCode Deploy environment or resource:

    ```
    jes.host=localhost
    jes.user=z/OS user ID
    jes.password=Password of the user. Set blank to use PassTicket authentication.
    jes.monitor.port=The port number for Job Monitor host server. The default port is 6715.
    
    ```


**Authenticating with a user ID and Password**

To use a password to authenticate, store the password in the jes.password property.

**Note:** As you complete the **Submit Job** or **Wait For Job** step, do not store the password directly in the **Password** field. The **Password** field contains plain text only and this field must be used to reference a property.

**Authenticating with PassTickets**

If you do not provide a password, the plug-in uses PassTicket authentication. You can use PassTickets authentication to eliminate the requirement to store user passwords in HCL UrbanCode Deploy.

To configure your system to use PassTickets, complete the following steps:

1.   Activate the **RACF PTKTDATA** class if it is not already active. The following code shows sample RACF commands: 

    ```
    SETROPTS GENERIC(PTKTDATA) SETROPTS CLASSACT(PTKTDATA) RACLIST(PTKTDATA) 
    RDEFINE PTKTDATA IRRPTAUTH.FEKAPPL.USER1 UACC(NONE) 
    ```

2.   To create a PTKTDATA profile that defines the secret key and the application name to which it applies for the Job Monitor, complete the following steps: 
    1.  Define the application name as **FEKAPPL**.
    2.  Define the key as a 64-bit number \(16 hex characters\).
    3.  Replace the key16 placeholder with a user-supplied 16 character hex string \(characters 0-9 and A-F\) as shown in the following sample RACF commands:

        ```
        RDEFINE PTKTDATA FEKAPPL UACC(NONE) SSIGNON(KEYMASKED(key16)) APPLDATA('NO REPLAY PROTECTION – DO NOT CHANGE') DATA('URBANCODE DEPLOY')
        ```

        The following example shows the command with the key16 value replaced:

        ```
        
        RDEFINE PTKTDATA FEKAPPL UACC(NONE) - DATA('URBANCODE DEPLOY') - APPLDATA('NO REPLAY PROTECTION - DO NOT CHANGE') - SSIGNON(KEYMASKED(0123456789ABCDEF))
        
        ```

    4.  Read the following scenarios:
        1.  If the **PTKTDATA** class is already defined, verify that it is defined as a generic class before you create the profile that was shown previously. The support for generic characters in the PTKTDATA class is new in the z/OS V1.7 release, with the introduction of a Java interface to PassTickets.
        2.  If a cryptographic product is installed and available on the system, you can encrypt the secured sign-on application key for added protection. Use the KEYENCRYPTED keyword instead of the KEYMASKED keyword. For more information, see the Security Server RACF Security Administrator's Guide \(SA22-7683\).
        3.  If the Rational Developer for System z or the Rational Team Concert server components are already installed on the system, the **PTKTDATA** profile might be defined already.
3.   To define a profile to generate a PassTicket, you must define the **IRRPTAUTH** profile in the **PTKTDATA** class. Then, this profile controls for which user ID a PassTicket is generated, as shown here: 

    |Operation|Profile name|Required access|
    |---------|------------|---------------|
    |Generate PassTicket|`IRRPTAUTH.application.target-userid`|Update|

4.   To set permissions for the UrbanCode Deploy Agent to generate a PassTicket so that the UrbanCode Deploy Agent generates a PassTicket, the user ID of the agent or the impersonated ID must have UPDATE access in the PTKTDATA profile that you created in the previous step. For more information, see the following RACF commands: 

    ```
    PERMIT IRRPTAUTH.FEKAPPL.USER1 CLASS(PTKTDATA) ID(AGNTUSR) ACCESS(UPDATE)
    ```

5.   To refresh the **PTKTDATA** class for the new profiles and permissions to take effect, see the following commands: 

    ```
    SETROPTS RACLIST (PTKTDATA) REFRESH
    
    ```


See the following PassTicket examples:

Example 1. Agent is started by user AGNTUSR. In a deployment process, a Job needs to be submitted on behalf of user USER1.

```
RDEFINE PTKTDATA IRRPTAUTH.FEKAPPL.USER1 UACC(NONE) 
PERMIT IRRPTAUTH.FEKAPPL.USER1 CLASS(PTKTDATA) ID(AGNTUSR) ACCESS(UPDATE) 
SETROPTS RACLIST (PTKTDATA) REFRESH

```

Example 2. Agent is started by user AGNTUSR. Allow this agent to submit jobs on behalf of any user.

```
RDEFINE PTKTDATA IRRPTAUTH.FEKAPPL.* UACC(NONE) 
PERMIT IRRPTAUTH.FEKAPPL.* CLASS(PTKTDATA) ID(AGNTUSR) ACCESS(UPDATE) 
SETROPTS RACLIST (PTKTDATA) REFRESH

```

Example 3. Agent is started by user AGNTUSR. Allow this agent to submit job on behalf of user AGNTUSR:

```
RDEFINE PTKTDATA IRRPTAUTH.FEKAPPL.AGNTUSR UACC(NONE) 
PERMIT IRRPTAUTH.FEKAPPL.AGNTUSR CLASS(PTKTDATA) ID(AGNTUSR) ACCESS(UPDATE) 
SETROPTS RACLIST (PTKTDATA) REFRESH

```

More JES security considerations are described in the IBM Developer for IBM Z documentation. For more information, see [JES Security](http://www-01.ibm.com/support/knowledgecenter/SSQ2R2_9.0.0/com.ibm.guide.hostconfig.reference.doc/topics/jessecurity.html?lang=en).

**Parent topic:** [Installing the z/OS agent](../../com.udeploy.install.doc/topics/zos_installing_ov.md)

