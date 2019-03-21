# Creating snapshots

To create a snapshot, you specify which version of components and processes to include in the snapshot. Typically, to create a snapshot you copy the components and processes from an environment where you deployed the application without errors.

1.  From the HCL® UrbanCode™ Deploy dashboard, click **Applications**, and then select an application. 
2.   On the application page, click **Snapshots**, and then click **Create Snapshot**. 
3.  Type the name of the snapshot in the **Name** field, and type a description in the **Description** field. 
4.  Click **Save**.The Component Versions page opens for the new snapshot. All the components in the application are listed.
5.  Add component versions to the snapshot. 
    -   Typically, you create a snapshot by copying versions of components from an environment in which you deployed and tested the application without errors. To copy the component versions in an environment, click **Select For All**, and then click **Copy from Environment**. Select the environment from which to copy component versions and processes. This procedure copies the currently deployed versions of the components from that environment.
    -   To create a snapshot that includes the component versions from another snapshot, click **Select For All**, and then click **Copy from Snapshot**.
    -   To select component versions individually, for each component click **Add** in the **Versions** column. After you click **Add**, click the **Versions** field to select a version of that component that is available in CodeStation. To select all the latest versions or to select all versions that match a name pattern, click **Select For All** and then select the appropriate option from the list.
6.  To refine the versions of the component processes in the snapshot, click **Configuration** \> **Advanced Settings**. By default, the most recently defined version of each component process and property is used. Latest is displayed in the **Versions** column, with the actual version in parentheses.
    -   To select a specific version of a process or property, click **Set Version** in the **Actions** column.
    -   To set all processes and properties to use the latest versions at the time of deployment, click **Reset All to Latest**. In this case, the processes and properties use the most recent versions that are available at the time you run the deployment.
    -   To set all processes and properties to use the most recent version that is currently available on the server, click **Set Latest Entries to Current**. In this case, the processes and properties use the most recent versions that are available at the time that you click **Set Latest Entries to Current**. Any changes that are made to processes and properties after this operation are not automatically absorbed into the snapshot.
    -   To permanently prevent any changes to the snapshot, click **Lock Configuration**.

        **Warning:** After you click this button, no changes can be made to the snapshot. This setting cannot be reversed.

7.   To lock snapshot component versions, using the Applications page, select an application, then click **Snapshot** \> **snapshot name** \> **Component Versions**. By default, the lock setting is determined by the option selected in the **Lock Snapshots** field on the Create Environment window. To lock previously unlocked component versions, click **Lock Versions**. 
8.   To lock a snapshot configuration, using the Applications page, select an application, then click **Snapshot** \> **snapshot name** \> **Configuration** \> **Advanced Settings**. By default, the lock setting is determined by the option selected in the **Lock Snapshots** field on the Create Environment window. To lock an unlocked snapshot configuration, click **Lock Configuration**. 

