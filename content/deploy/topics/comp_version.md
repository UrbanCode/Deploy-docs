# Component versions {#comp_version .concept}

Each time a component's artifacts are imported into the repository, including the first time, a separate version is stored in CodeStation. Versions can be assigned automatically by IBM® UrbanCode® Deploy, applied manually, or come from a build server.

Every time a component's artifacts are modified and imported, a new version of the component is created and an entry is made in the Component Version Import log. So a component might have several versions in CodeStation, and each version is unique.

**Note:** By default, the component version import log is cleaned up every 24 hours. Only the most recent 100 entries are maintained in the log after cleanup.

Artifacts can be imported automatically or manually. By default, a complete copy of an artifact's content is imported into CodeStation. When you copy the artifact to CodeStation, the original artifact content is never modified.

A version can be full or incremental. A full version contains all component artifacts; an incremental version contains only artifacts that are different from the previous version. When performing an incremental import you only need to upload only the changed artifacts. Artifacts that are the same as the base version do not need to be uploaded.

Storing artifacts in CodeStation provides several benefits, such as tamper-proof storage, and the ability to review and validate artifacts with the IBM UrbanCode Deploy user interface. But if you have storage concerns or use a tool like Maven, you can limit CodeStation to using references to the artifacts instead of copying them into CodeStation.

**Note:** Do not give component versions the name `latest`, `latestVersion`, or `newest`. These names are reserved to represent the most recently created version for certain CLI commands, including [requestApplicationProcess](../../com.ibm.udeploy.api.doc/topics/udclient_requestapplicationprocess.md) and [createSnapshot](../../com.ibm.udeploy.api.doc/topics/udclient_createsnapshot.md). You cannot use these keywords to represent component versions in the web interface.

-   **[Tracking environment inventory for components](../topics/comp_version_tracking.md)**  
You can track the environment inventory for each component by clicking the component and then going to the **Usage** tab.
-   **[Importing versions manually](../topics/comp_version_import.md)**  
If the component does not import new versions automatically, you can import versions manually.
-   **[Cleaning up component versions](../topics/settings_system_preview.md)**  
You can configure the server to reduce the number of component versions by archiving them. You can specify global cleanup settings, cleanup settings for individual components, and cleanup settings for specific environments.
-   **[Restoring archived component versions](../topics/comp_version_restore.md)**  
You can restore component versions by reloading archive files.
-   **[Deleting versions](../topics/comp_version_delete.md)**  
If specific component versions meet the criteria for deletion, you can delete them.

**Parent topic:** [Components](../topics/comp_ch.md)

