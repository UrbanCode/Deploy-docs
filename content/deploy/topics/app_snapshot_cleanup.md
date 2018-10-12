# Cleaning up snapshots {#app_snapshot_cleanup .task}

You can configure the server to reduce the number of snapshots by deleting old snapshots. You can specify global cleanup settings and cleanup settings for specific environments.

Snapshot cleanup runs daily, at the same time as component version cleanup. The server deletes snapshots that do not meet any of the criteria for snapshots to keep. The effect is the same as if you delete the snapshot manually. These snapshots are not archived and are not recoverable.

When cleaning up snapshots, the server retrieves the settings from the **Settings** \> **System Settings** \> **Artifact Cleanup** options first. Then it retrieves the settings for individual environments, which override the system settings. If any of these settings specify to keep the snapshot, it is not deleted.

The settings for snapshot cleanup specify a number of days to keep snapshots. This time period is measured from the day that the snapshot is no longer the most recently deployed snapshot in an environment. For example, assume that the **Default Application Snapshot Retention \(days\)** system setting is set to 30 days. If a snapshot is deployed on day 1 and another snapshot is deployed on day 10, the first snapshot can not be cleaned up until day 40.

The system setting also refers to the number of days since the snapshot was created. If a snapshot was created fewer days ago than the **Default Application Snapshot Retention \(days\)** system setting, it is kept.

The criteria for keeping or deleting snapshots are as follows:

-   If the snapshot is the most recently deployed snapshot in any environment, it is kept.
-   In any environment, if the snapshot was the most recently deployed snapshot within the number of days in the system setting or the environment setting, it is kept.
-   If the snapshot age in days is less than the system setting, it is kept.

If none of these criteria are true, the snapshot is deleted, even if it was deployed to an environment in the past.

1.   Specify the system snapshot cleanup settings: 

    1.   Click **Settings** \> **System Settings**. 
    2.   Under **Artifact Cleanup**, in the **Default Application Snapshot Retention \(days\)** field, specify how long to retain snapshots, in days. 
    3.   Click **Save**. 
    For information about the other settings in this section, see [Cleaning up component versions](settings_system_preview.md).

2.   Specify cleanup settings for individual environments. These settings override the system settings.
    1.   Click **Applications**, click an application, click an environment, click **Configuration**, and then click **Basic Settings**. 
    2.   Clear the **Use Default Artifact Cleanup Settings** check box. 
    3.   In the **Days to Retain Application Snapshots** field, specify how long to keep a snapshot after it is not the most recently deployed snapshot in the environment. 
    4.   Click **Save**. 

**Parent topic:** [Snapshots](../topics/app_snapshot.md)

