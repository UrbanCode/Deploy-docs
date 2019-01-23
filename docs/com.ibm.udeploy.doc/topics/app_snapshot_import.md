# Importing and exporting snapshots

You can import and export snapshots to transfer snapshots and component version artifacts to different servers.

Make sure that the application and the components in the snapshot exist on the target server.

**Note:** Exporting snapshots in this way includes only the versions of the components that are in the snapshot. However, the exported snapshot always includes the most recent versions of component processes.

To export a snapshot, go to the **Snapshots** tab for an application and next to the snapshot, click **Export**. The server stores the snapshot, the component versions, and the plug-ins that the components use in an archive file.

To import the snapshot on another server, open the application, go to the **Snapshots** tab, and click **Import Snapshots**.

**Note:** You must create the archive file that contains the snapshot on a server that uses the same version of HCL® UrbanCode™ Deploy as the destination server.

**Parent topic:** [Snapshots](../topics/app_snapshot.md)

