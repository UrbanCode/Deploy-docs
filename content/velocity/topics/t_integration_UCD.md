# Configuring UrbanCode Deploy integrations {#t_integration_UCD .task}

Use UrbanCode Deploy applications in your deployments and pipelines.

Obtain a token from your Urban Code Deploy server. When you create the UrbanCode™ Deploy token, specify **admin** as the user.

This task requires that you are an UrbanCode Velocity administrator.

After you configure an integration, [create tasks to run UrbanCode Deploy applications during your deployments](../../com.ibm.crelease.doc/topics/cr_taskType_UCD.md#). You can also add applications to your pipeline stages and run them that way.

1.   Click **Settings** \> **Integration**. A list of defined integrations with current information about each integration is displayed in a table.
2.   Click **Add Integration**, and then select **UrbanCode Deploy**. 
3.   In the Add UrbanCode Deploy Integration window, enter a name for the integrations, and in the **UrbanCode Deploy server URL** field, define the URL. The format is `HTTPS://hostname:port`. For example, `HTTPS://sampleUCD:8443`.

    **Note:** If you are running UrbanCode Deploy locally, you can substitute `HTTPS://host.docker.internal:port` in place of `localhost`.

4.   In the **UrbanCode Deploy access token** field, paste the token from UrbanCode Deploy. 
5.   Click **Save**. The initial synchronization includes four months of data. Depending on the amount of data, this process can take some time.

Synchronization occurs every fifteen minutes but you can synchronize any time by selecting **Resync** on the Integration page. To prevent synchronization, select **Disable** on the Integration page.

**Parent topic:** [Managing integrations](../topics/c_node_integrations.md)

