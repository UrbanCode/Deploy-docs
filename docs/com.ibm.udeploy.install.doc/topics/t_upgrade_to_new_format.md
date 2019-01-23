# Automatic upgrades of files stored in the server CodeStation

When you upgrade to HCL® UrbanCode™ Deploy version 6.1 or later, the server automatically upgrades all artifacts that are stored in its CodeStation.

When you start the server, the CodeStation upgrade process starts automatically and runs in the background. The upgrade proceeds sequentially through all versions. Versions are upgraded one at a time so that the process does not cause excessive IO and performance issues. There is no server downtime during the upgrade process.

Before the upgrade, if the server is running on Linux™ and you want to spread the files over multiple disks for the upgrade, you can use soft links. The upgrade creates the following folders:

-   app\_data/var/repository/blob
-   app\_data/var/repository/ptr
-   app\_data/var/repository/stage

Most of the files are stored in the folder app\_data/var/repository/blob. Within this folder, files are stored in up to 256 subfolders based on a hexadecimal hash, such as app\_data/var/repository/blob/00 or app\_data/var/repository/blob/01. If you want to spread the files over multiple disks, create these folders before the upgrade and link the folders to the appropriate disks. In this case, the upgrade stores the files on the targeted disks.

While the upgrade process is in progress, you can continue working in the deployment tool. You can request deployments of a specific artifact version at any time, even before the server upgrades the version. When you send a deployment request for a specific version, the server checks whether the version is upgraded. If version is not upgraded, the upgrade process starts immediately.

For example, if you request a deployment with a specific component version, but it is not upgraded, the server upgrades the version before it continues with the deployment.

To monitor the upgrade process, click **Settings** \> **CodeStation**, and view the progress bar and percentage. When the upgrade process finishes, the progress bar closes.

**Parent topic:** [Upgrading and migrating](../../com.ibm.udeploy.doc/topics/c_node_upgrading.md)

