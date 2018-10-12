# Cleaning up component versions {#settings_system_preview .task}

You can configure the server to reduce the number of component versions by archiving them. You can specify global cleanup settings, cleanup settings for individual components, and cleanup settings for specific environments.

The server archives a full or incremental component version if the version does not meet any of the criteria for versions to keep. When archiving versions, the server retrieves the settings from the **Settings** \> **System Settings** \> **Artifact Cleanup** options first. Then it retrieves the settings for the individual components, which override the system settings. Finally, it checks the settings on the environments to which the component has been deployed. If any of these settings specify to keep the component version, it is not archived.

These settings include a number of days for which to retain versions and a number of versions to keep. The server settings and the component settings refer to the creation date of the version. For example, if the server settings or component settings keep versions for 30 days, a version is not archived until its creation date is more than 30 days in the past. Similarly, if the server settings or component settings keep the 10 most recent versions, a version is not archived until there are 10 more recently created versions. Component settings override server settings for that component.

By contrast, the environment settings refer to the most recent deployment date of the version. For example, if the environment settings keep versions for 30 days, a version is not archived if it has been deployed in the last 30 days. If an environment does not have settings, the server uses the system settings instead. For example, if the server settings keep versions for 30 days and the version was created more than 30 days ago but was deployed to an environment within 30 days, the version is kept.

The server uses the following criteria to determine which versions to keep and which to archive:

First, the server checks the settings on the component. If the component has settings to keep versions, the server uses those settings. Otherwise, the server uses the defaults in the server settings.

-   If the number of days to keep versions is set to -1, the version is kept.
-   If the number of versions to keep is set to -1, the version is kept.
-   If the version was created within the number of days to keep versions, it is kept.
-   Based on the number of versions to keep, if the version is in the most recently created versions, it is kept.

Then, the server checks the settings for each environment to which the component version has been deployed. If an environment does not have settings, the server uses the system settings for that environment. In the context of environments, the settings refer not to the creation date of the component but the date of the most recent deployment of that component. For example, if the system settings keep the 20 most recent versions, and the version is one of the 20 most recently deployed versions in an environment, the version is kept. Using these settings, the server uses the following criteria:

-   If the version is currently deployed to any environment or is listed in the inventory of any resource, it is kept.
-   If the version is part of any snapshot, it is kept.
-   If the number of days to keep versions is set to -1 in any of the environments, the version is kept.
-   If the number of versions to keep is set to -1 in any of the environments, the version is kept.
-   If the version has been deployed within the number of days to keep versions, it is kept.
-   Based on the number of versions to keep, if the version is in the most recently deployed versions, it is kept.

If none of these criteria are true, the component version and the artifacts in it are archived, even if the version was deployed to an environment in the past.

**Note:** Beginning with version 6.1, the server stores full copies of each file in each component version, even if the files are duplicates.

1.   Specify the global component version cleanup settings: 
    1.   Click **Settings** \> **System Settings**. 
    2.   Under **Artifact Cleanup**, in the **Daily Cleanup Start Time** field, specify the hour of the day to start the cleanup process. 
    3.   In the **Default Application Snapshot Retention \(days\)** field, specify the minimum age in days to save snapshots. For more information, see [Cleaning up snapshots](app_snapshot_cleanup.md).
    4.   In the **Default Component Version Retention \(days\)** field, specify the minimum age in days to save a component version. For example, to keep all component versions that are 5 days old or newer, specify 5. If you specify -1, all versions are saved, regardless of the setting in the **Default Number of Versions to Retain** field.
    5.   In the **Default Number of Versions to Retain** field, specify the minimum number of versions to keep. For example, to save the five most recent component versions, specify 5. If you specify -1, all versions are saved, regardless of the settings in the **Default Component Version Retention \(days\)** field.

        When the server runs the cleanup, it deletes or archives all component versions that are older than the minimum age. However, the server retains at least the number of versions in the **Default Number of Versions to Retain** field.

    6.   In the **Archive Path** field, specify the path of the location on the server to write compressed versions of each version that is archived. If you do not specify a path, then the server does not store the component versions that it removes.
    7.   To preview the component versions to be archived the next time that an archive file is created, on the **System Settings** tab, click the **Preview Version Cleanup** link, and select a component. 
    8.   Click **Save**. 
2.  Specify cleanup settings for individual components.These settings override the global settings.
    1.  Click **Components**, click a component, go to the **Configuration** tab for the component, and then click **Basic Settings**.
    2.   Clear the **Use Default Component Cleanup Settings** check box. 
    3.   In the **Days to Retain Versions** field, specify the minimum age in days to save a component version. 
    4.   In the **Number of Versions to Retain** field, specify the minimum number of versions to keep. 
    5.  Click **Save**.
3.   Specify cleanup settings for individual environments. These settings override the global settings.
    1.   Click **Applications**, click an application, click an environment, click **Configuration**, and then click **Basic Settings**. 
    2.   Clear the **Use Default Component Cleanup Settings** check box. 
    3.   In the **Days to Retain Versions** field, specify the minimum age in days to save a component version. If you set bot both component and environment settings, the higher value is used. 
    4.   In the **Number of Versions to Retain** field, specify the minimum number of versions to keep. 
    5.   Click **Save**. 

**Parent topic:** [Component versions](../topics/comp_version.md)

