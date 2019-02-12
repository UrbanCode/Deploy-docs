# Server settings

These tables list the settings for several system-wide settings for the server.

|Field|Description|
|-----|-----------|
|**External Agent URL\***|This is the URL that the HCL® UrbanCode™ Deploy server provides to agents as their point of contact. When an agent wants to contact the server, it retrieves this URL and opens a connection on it. This URL must point to the HTTP or HTTPS port of the server.|
|**External User URL\***|The URL that users enter to connect to the HCL UrbanCode Deploy server. The URL is also used when creating a notification template and when integrating blueprints with HCL UrbanCode Deploy.|
|**Validate Agent IP**|Requires that the agent IP and host name are validated against values that are used the first time that the agent is connected to the HCL UrbanCode Deploy server.|
|**Skip Property Updates for Existing Agents**|When this toggle button is set to On, when new agents come online, the server does not update their properties. This improves performance, but in this case, agent properties can become out of date.|
|**Enable UI Debugging**|Facilitates debugging with the user interface. If this setting is enabled, the performance of the user interface might be affected.|
|**Require a Comment For Process Design Changes**|Requires that the user provides a comment when the user changes processes.|
|**Components copy to CodeStation by default**|If this toggle is set to On, newly created components copy artifacts to CodeStation by default. You can still change this setting on individual components.|
|**Default Locale**|The default language for the user interface.|
|**Default Snapshot Lock Type**|Determines the default lock type when users create snapshots. Lock types are the following values: **Only Component Versions**, **Only Configuration**, or **Component Versions and Configuration**. The initial value is **Component Versions and Configuration**. Changes are effective after the server is restarted.|

|Field|Description|
|-----|-----------|
|**Components copy to CodeStation by default**|If this toggle is set to On, newly created components copy artifacts to CodeStation by default. You can still change this setting on individual components.|
|**Enforce Deployed Version Integrity**|When this toggle button is set to On, deployed component version artifacts cannot be changed.|
|**Automatic Version Import Check Period \(seconds\)\***|The number of seconds between the times that HCL UrbanCode Deploy polls components for new versions. If this value is changed, the server must be restarted before the change becomes effective. Set this value no lower than 15 seconds.|
|**Use Agent Tag For Integration**|Enables any agent that is identified by a specific tag to import component versions. If this setting is selected, the **Agent Tag for version imports** field is shown. Otherwise, the **Agent for Version Imports** field is displayed. For information about tagging objects, see [Adding tags to objects](../../com.udeploy.doc/topics/addingtags_tsk.md#)|
|**Agent for Version Imports**|The agent that is used to import component versions. The agent must have access to component artifacts. The agent becomes the default agent for new components. This value can be overridden when a component is created. This field is displayed if the **Use Agent Tag for Integration** toggle button is set to Off. To import artifacts from the server location, install an agent in the same location and specify that agent.|
|**Agent Tag for version imports**|Any agent with the specified tag can import component versions. All tagged agents must have access to the artifacts. Tagged agents become the default values for new components. This value can be overridden when a component is created. This field is displayed if the **Use Agent Tag for Integration** toggle button is set to On.|
|**Enable Safe Edit of Component Processes**|Enables you to test component processes before making them available in normal environments. Make updates to your component process, test those updates safely, and then promote to a new version when you are ready, when toggle is set to On.|

|Field|Description|
|-----|-----------|
|**Hour to Clean Versions\***|The time when versions are cleaned. The value must be an integer from 0 \(midnight\) to 23 \(11 pm\). To preview the component versions that are scheduled for cleaning, click **Preview Version Cleanup**. See [Cleaning up component versions](../../com.udeploy.doc/topics/settings_system_preview.md).|
|**Days to Keep Versions\***|The number of days component versions are kept, by default. A value of `-1` means that they are kept indefinitely. Component and environment settings can override this setting.|
|**Number of Versions to Keep\***|The number of component versions to keep, by default. A value of `-1` specifies that all are kept. Component and environment settings can override this setting.|
|**Archive Path**|The path where the compressed file that contains the archived component versions is written. If this field is blank, the compressed file is not written, and no archive is kept.|
|**Preview Version Cleanup**|To see the versions that are archived using the current settings, click **Preview Version Cleanup**. See [Cleaning up component versions](../../com.udeploy.doc/topics/settings_system_preview.md).|

|Field|Description|
|-----|-----------|
|**Enable Deployment History Cleanup**|When this toggle button is set to On, deployment history files are reduced. See [Cleaning up deployment history files](../../com.udeploy.doc/topics/depl_history_cleanup.md).|
|**Daily Cleanup Start Time**|The hour that the daily cleanup process starts.|
|**Daily Cleanup Duration \(hours\)**|The number of hours that the cleanup process runs daily.|
|**Days to Retain Deployment History**|The number of days to retain deployment history. This setting can be overridden with the related environment setting.|

|Field|Description|
|-----|-----------|
|**Enable Audit Log Entries for Read Events**|When this option is disabled, no READ events are recorded in the audit log.|
|**Enable Audit Log Cleanup**|When this option is enabled, audit log entries older than the number of days specified in the **Days to Retain Audit Log Entries** field are removed beginning at the time specified by the **Daily Cleanup Start Time** field. By default, this option is disabled. See [Automatically downloading audit log files](../../com.udeploy.doc/topics/troubleshoot_logDownload.md).|
|**Daily Cleanup Start Time**|If **Enable Audit Log Cleanup** is enabled, the time the audit log cleanup starts. The default value is 12:00 AM.|
|**Days to Retain Audit Log Entries**|If **Enable Audit Log Cleanup** is enabled, the number of days that audit log records are retained. The default value is 30.|

|Field|Description|
|-----|-----------|
|**Minimum Password Length\***|Determines the minimum length for passwords.|
|**Require Complex Passwords**|If selected, passwords must contain at least two of the four character classes and must meet the specified minimum length requirement. The 4 classes are uppercase, lowercase, digits, and special characters.|
|**Discovery Auth Token Expiration Delay\(seconds\)**|Delay in seconds for auth tokens that are created for Auto Discovery Steps to expire. Must be 300 seconds or more.|
|**Configure Auth Token Expiration Delay\(seconds\)**|Delay in seconds for auth tokens that are created for Auto Configure Steps to expire. Must be 300 seconds or more.|
|**Version Import Auth Token Expiration Delay\(seconds\)**|Delay in seconds for auth tokens that are created for Version Import Steps to expire. Must be 300 seconds or more.|
|**Plugin Step Auth Token Expiration Delay\(seconds\)**|Delay in seconds for auth tokens that are created for Plug-in Steps to expire. Must be 300 seconds or more.|
|**Use Default Auth Token Restriction if not specified**|Enable the default authentication token restriction for processes that are created in HCL UrbanCode Deploy 6.2.6.x and earlier. For these versions, the default token is applied to the most current process version but not other versions. If you want to apply the default token restriction to all pre-6.2.7 process versions, turn on this option. By default, the option is turned off. For more information, see [Restricting authentication tokens](security_token_restrict.md).|

|Field|Description|
|-----|-----------|
|**WinRS Agent**|The agent that is used to run agent installation processes on Windows™ computers. The WinRS agent is configured to use the Windows winrs command, which enables remote systems to run Windows commands. Typically, the agent that is designated as the WinRS agent is used exclusively for this purpose. **Note:** A WinRS agent must be designated before agents can be installed remotely on Windows computers.

|
|**WinRS User**|The user name for Windows Remote Management.|
|**WinRS Password**|The user password for Windows Remote Management.|

|Field|Description|
|-----|-----------|
|**Mail Server Host**|The host name of the mail server that is used for notifications. HCL UrbanCode Deploy can send notifications to users based on user-configured trigger events \(to set up notifications, see [Creating Notifications in a Notification Scheme](../../com.udeploy.doc/topics/notify_create.md)\). HCL UrbanCode Deploy requires an external SMTP mail server to send messages. To disable notifications, leave the field blank.|
|**Mail Server Port**|The SMTP port that is used by the notifications mail server.|
|**Secure Mail Server Connection**|Specifies whether the SMTP connection is secure. The default value is **Off**.|
|**Mail Server Sender Address**|The sender address for email notifications.|
|**Mail Server Username**|The user name for sending email notifications. Some email servers and firewalls treat emails with different sender and user names suspiciously. Therefore, consider specifying the same name for both fields.|
|**Mail Server Password**|The user password for sending email notifications.|

|Field|Description|
|-----|-----------|
|**Enable "Show Inactive" Links**|By default, user-created objects that were made inactive in product versions earlier than 6.0, are hidden. If this option is selected, hidden objects are displayed and can be used or deleted.|
|**Enable "Prompt On Use"**|Controls whether user-entered values can be specified at process run time. If this parameter is inactive \(the default setting\), values must be entered on the plug-in step during process creation. If this option is selected, process designers have the option of requiring users to enter values during run time.|
|**Enable "Allow Failure"**|Shows an **Allow Failure** check box on steps.|
|**Fail Processes With Unresolved Properties**|Any running process that cannot resolve a property automatically fails. This setting is enabled by default.|

|Field|Description|
|-----|-----------|
|**Automatic Agent Licensing**|If this toggle button is set to On, the HCL UrbanCode Deploy server automatically attempts to license agents as they connect to the server. See [Applying licenses to servers and agents](../../com.udeploy.install.doc/topics/license_apply.md).|
|**Server License Type**|Contains the license type that is retrieved from the Rational Common Licensing server. See [License scenarios](../../com.udeploy.install.doc/topics/license_scenarios.md).|
|**RCL Server Path**|In most cases, specify the host name and port of the Rational Common Licensing server. The format is port@hostname. For more information, see [Applying licenses to servers and agents](../../com.udeploy.install.doc/topics/license_apply.md).|
|**Download License Log**|Download the license usage log files. The log file contains all license violations. Messages are listed in descending order of violation time, so the most recent violation is displayed first.|

**Parent topic:** [Server settings and configuration](../../com.udeploy.doc/topics/settings_ch.md)

**Parent topic:** [Managing security](../../com.udeploy.admin.doc/topics/security_ch.md)

