# Cleaning up deployment history files {#proc_history_cleanup .task}

You can clean up deployment history files to reduce database and file system storage that IBM® UrbanCode® Deploy uses.The administrator can enable the deployment history cleanup and specify when the cleanup process begins, the duration of the cleanup, and the number of days to retain the process history. Administrators can also turn off deployment history cleanup. Other users, depending on their privileges, can use the deployment history cleanup process for specific environments. However, while the administrator has the **Enable Deployment History Cleanup** switch turned off, even when a user selects **Use Deployment History Cleanup** for an environment, the deployment history cleanup process remains turned off. By default, the deployment history cleanup enablement settings in both the administrator and environment settings are turned off.

**Important:** The deployment history cleanup process deletes all records in the database and the file system that are related to the deployments that you're deleting. No record that the deployment ever happened remains. The cleanup cannot be undone. Carefully choose the items that you delete. Despite these settings, no deployments that are associated with active inventory of any type are deleted in the cleanup process. Nothing that is currently deployed to any environment is deleted.

To enable or disable deployment history cleanup and specify other settings, an administrator completes these steps:

1.  In IBM UrbanCode Deploy, click the **Settings** tab, and then in the **System** column, click **System Settings**.
2.  Scroll to the **Deployment History Cleanup** area.
3.  Set **Enable Deployment History Cleanup** to **On**.
4.  In **Daily Cleanup Start Time**, select the hour to start the daily cleanup process.
5.  In **Daily Cleanup Duration \(hours\)**, specify the number of hours for the cleanup process to run.
6.  In **Days to Retain Deployment History**, specify the default number of days to keep the deployment history before the cleanup process removes the history.

To enable deployment history cleanup for specific environments, users with the correct privileges complete the following steps.

**Tip:** For the cleanup process to start and run according to specifications, the cleanup process must be turned on in **Deployment History Cleanup** in System Settings and **Use Deployment History Cleanup** must be selected in environment settings.

|**Enable Deployment History Cleanup** switch in System Settings \(administrator's setting\)|**Use Deployment History Cleanup** check box in environment settings|Result|
|-------------------------------------------------------------------------------------------|--------------------------------------------------------------------|------|
|On|Selected|Cleanup starts as specified for deployments that are associated with this environment.|
|On|Cleared|Cleanup does not start for deployments that are associated for this environment.|
|Off|Selected|Cleanup does not start for deployments that are associated with this environment.|

For example, Assume that you have two environments: Environment A and Environment B. In the Environment B settings, the **Use Deployment History Cleanup** check box is cleared. The check box is selected for Environment A. When the cleanup process starts, the deployments that are associated with Environment B are not removed.

1.  In IBM UrbanCode Deploy, click the main **Applications** tab, and create an application or select a listed application.
2.  Click **Create Environment** or click the **Change** icon ![](../images/change.jpg) for a selected application environment.
3.  Complete the fields and make selections, and then select **Use Deployment History Cleanup**.
4.  Do one of these steps:
    1.  Select **Use Default Deployment History Retention** to keep deployment history details for the number of days that the administrator specified.
    2.  In **Days to Retain Deployment History**, specify the number of days to keep deployment history details.

When cleanup begins, a progress indicator shows details about the cleanup process.

If the date is 14 December 2016, and the following settings are used, cleanup removes the items that are listed.

-   **Enable Deployment History Cleanup** \(System Settings:\): **On**
-   **Daily Cleanup Start Time** \(System Settings\): **9:00 PM**
-   **Daily Cleanup Duration \(hours\)** \(System Settings\): **3**
-   **Days to Retain Deployment History** \(environment settings\): `15`
-   **Use Deployment History Cleanup** \(environment settings\): selected
-   **Use Default Deployment History Retention** \(environment settings\): selected

At 9:00 PM on 14 December 2016, the deployment history begins to run for 3 hours. During the 3 hours, all records of the deployment that are 15 days old or older are deleted, including records of component processes that are run and step logs from the processes. Three hours might be insufficient to delete all records that meet the cleanup criteria. In that case, cleanup resumes operations the next day as scheduled. If you need to clear more disk space, increase the cleanup duration.

**Tip:** If the cleanup settings are changed before 9:00 PM 14 December, then items that are deleted are not be the same as in this example. The settings can changed after this date. The settings might be changed numerous times. At any time, the administrator or users with privileges can change whether the cleanup process runs, what cleanup removes, when cleanup starts, and how long cleanup runs.

**Parent topic:** [Deploying](../topics/deployment_ov.md)

