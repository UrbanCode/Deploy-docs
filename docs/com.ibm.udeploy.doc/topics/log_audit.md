# Viewing logs

You can view logs from the **Settings** \> **System** page.

To view audit logs, you must be in an administration role, specifically a role with the Web UI **Settings Tab** permission.

The audit log contains entries of user activity. An entry is created whenever a user does on of the following activities:

-   Performs an activity that is granted by a security permission, such as creating a component, or creating an application. These activities include permissions granted by the server configuration security type, such as managing plug-ins, system properties, and statuses. Permissions are based on the team roles that are assigned to the user.
-   Modifies security settings, such as creating a role, or assigning a user to a role.
-   Performs an authentication activity, such as logging on to the Web UI, or accessing the REST API.
-   
1.   Review the log files. 
    -   To view the audit log, log in as an administrator and click **Settings** \> **Audit Log**.

        To filter the log, type in the fields at the top of each column. For example, to view the admin user's activities, select **admin** in the **User Name** filter field.

        To show only actions in which an element was created, specify CREATE in the **Event Type** filter field.

        To remove old entries from the audit log, click **Cleanup Log**, specify the date and time, and click **Submit**. All log entries prior to that date and time are permanently deleted.

        **Note:** Starting with version 6.2.6, the activities of the built-in administrator user \(with the user name admin\) generate entries in the Audit Log page.

    -   To view the diagnostic logs, **Settings** \> **Diagnostics**. The tabs on this page show diagnostic information:

        -   ****REST Call Log****

            This log shows all the requests that the server receives, including requests from the web interface, the REST API, and the command-line client. You can filter this table by typing values in the fields at the top and then pressing Enter.

        -   ****Metadata Indexing****

            This page shows the state of the server indexes, which store information about elements such as components and processes. If indexing is not complete, you might not be able to use certain filters or to open certain processes. Indexing happens after certain server upgrades.

        -   ****Java Thread Dumps****

            On this page, you can export information about the current state of all Java™ threads on the server.

        To download a diagnostic report that contains this information and the server logs, click **Settings** and next to the **Diagnostics** link, click **Download**.

        You can also get detailed logs for processes, including the all of the information and logs from each step. To download these logs, open the process request, and click **Download All Logs**.

    -   To view the server output log, click **Settings** \> **Output Log**.

        The HCL® UrbanCode™ Deploy server log file is normally found in the following location: server\_installation\_directory/var/log/deployserver.out. You can open log files directly.

        The information that is written to the log file is determined by the settings in the log4j.properties file. This file is found at app\_data/conf/server/log4j.properties. You can edit the file directly, or you can open it in the server by clicking **Settings** \> **System** \> **Logging**.


**Parent topic:** [Logging](../topics/log_ov.md)

