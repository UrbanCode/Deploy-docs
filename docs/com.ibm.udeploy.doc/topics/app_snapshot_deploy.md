# Deploying snapshots

After you create a snapshot, you can deploy the snapshot to an environment.

Deploying a snapshot deploys the components in the snapshot. The components are deployed in the order in which they were added to the snapshot or to the environment on which the snapshot is based.

1.  From the HCL® UrbanCode™ Deploy dashboard, click **Applications**, and then select an application. 
2.  On the application page, click **Snapshots**, and then select a snapshot.The environments that are defined for the application are listed at the bottom of the Dashboard page.
3.  For the environment where you plan to deploy the snapshot, click the **Request Process** icon.
4.  To deploy component versions whether or not they are already deployed, clear the **Only Changed Version** check box.By default, the **Only Changed Version** check box is selected so that only changed versions of components are deployed.
5.  Select the deployment process to run from the **Process** list. 
6.  To run the process in the future, select the **Schedule Deployment** check box.If you select the **Schedule Deployment** check box, more fields become available so that you can specify the date and time to run the process, and configure the process to run on a recurring basis.
7.  Click **Submit**.Unless you scheduled the process to run in the future, the application process starts and deploys the snapshot.

**Parent topic:** [Snapshots](../topics/app_snapshot.md)

