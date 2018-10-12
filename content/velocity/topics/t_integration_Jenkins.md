# Configuring Jenkins integrations {#t_integration_Jenkins .task}

Manage Jenkins jobs with your deployments and pipelines.

Obtain the UrbanCode Velocity plug-in and install it in your Jenkins instance. To complete an integration, you paste UrbanCode Velocity credentials into Jenkins.

**Note:** In Jenkins, you must have admin privileges to install the plug-in.

This configuration makes Jenkins jobs available to pipelines and deployment plans. You can run Jenkins jobs with UrbanCode Velocity and use the output in later tasks. After you configure an integration, [add Jenkins tasks to deployment plans](../../com.ibm.crelease.doc/topics/cr_taskType_Jenkins.md#) and pipeline stages.

1.   Click **Settings** \> **Integration**. A list of defined integrations with current information about each integration is displayed in a table.
2.   Click **Add Integration**, and then select **Jenkins**. 
3.   In the Setup Jenkins Integration window, in the **Name** field, enter a name for the integrations. 
4.   In the **Integration ID** field, copy the ID and then paste it into the corresponding field in your Jenkins instance,**Manage Jenkins** \> **Configure System** \> **UrbanCode Deploy**. 
5.   In the **Integration token** field, copy the token and then paste it into the corresponding field in Jenkins. 
6.   Click **Save**. Depending on the amount of data,the initial integration can take some time. Synchronization occurs every minute. To prevent synchronization, select **Disable** on the Integration page.

After the initial integration, you can add Jenkins tasks to deployment plans and select any of the integrated jobs. Similarly, you can add Jenkins jobs to pipeline stages.

**Parent topic:** [Managing integrations](../topics/c_node_integrations.md)

