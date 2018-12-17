# Snapshots

A snapshot is a collection of specific versions of components and processes. Typically, a snapshot represents a set of component versions that are known to work together. In most cases, snapshots include all of the components in an application.

A snapshot is typically created when a successful deployment runs in an uncontrolled environment, where there are no approval gates. Snapshots can be created in controlled environments too. When a snapshot is created, a picture of the application's current state is captured. As the application components move from one environment to another, HCL® UrbanCode™ Deploy ensures that the exact versions and processes that you selected are used in each environment.

Snapshots can help manage complex deployments, which have multiple environments and development teams. For example, after you test and confirm that team A's component works with team B's component, you can create a snapshot. Then, as development progresses, you can create more snapshots to model the effort and drive the entire deployment, coordinating versions, configurations, and processes.

-   **[Creating snapshots](../topics/app_snapshot_create.md)**  
To create a snapshot, you specify which version of components and processes to include in the snapshot. Typically, to create a snapshot you copy the components and processes from an environment where you deployed the application without errors.
-   **[Deploying snapshots](../topics/app_snapshot_deploy.md)**  
After you create a snapshot, you can deploy the snapshot to an environment.
-   **[Comparing snapshots](../topics/app_snapshot_compare.md)**  
You can compare two snapshots to see differences in the files that they contain.
-   **[Previewing snapshots](../topics/app_snapshot_preview.md)**  
You can preview an application snapshot before you deploy it to see the upcoming changes in resources and properties.
-   **[Cleaning up snapshots](../topics/app_snapshot_cleanup.md)**  
You can configure the server to reduce the number of snapshots by deleting old snapshots. You can specify global cleanup settings and cleanup settings for specific environments.
-   **[Importing and exporting snapshots](../topics/app_snapshot_import.md)**  
You can import and export snapshots to transfer snapshots and component version artifacts to different servers.

**Parent topic:** [Applications](../topics/applications_ch.md)

