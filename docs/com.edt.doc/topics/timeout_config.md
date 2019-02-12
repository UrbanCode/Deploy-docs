# Creating a HCL UrbanCode Deploy timeout configuration file

You can create a configuration file to store the default timeout values for the blueprint designer to use with HCL® UrbanCode™ Deploy agent, process, and server communication variables.

When you provision images that contain HCL UrbanCode Deploy components, you must allow time for the server to respond. You provide timeout values to specify how long to wait for agents to install, for component processes to complete, and for the HCL UrbanCode Deploy server to return REST API calls to the blueprint designer. You can create a configuration file to store these timeout values, and the values that you set are applied to each blueprint that you provision. If you do not create a configuration file, you can specify these timeout values in the HCL UrbanCode Deploy resources of each blueprint that you provision. See [HCL UrbanCode Deploy resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_ucd_ov.md#). If you create a configuration file and specify timeout values in the blueprint, when you provision, the blueprint designer uses the timeout values that you specify in the blueprint.

1.   On the computer that hosts the Heat engine, create a configuration file. In the /usr/lib/heat/ibm-sw-orch/heat/ folder, create a file that is named user\_settings.conf. Use the following template for the file.

    ```
    [user-settings]
    timeout:
      {
        "agent": 300,
        "component_process": 300,
        "ucd_client": 300,
        "agent_subgroup": 30,
        "sleep_delay": 10,
        "application_process":480
      }
    
    ```

    Provide appropriate values, in seconds, for the parameters. In the previous example, the values for the agent, component\_process, and ucd\_client timeout timeouts are each set to 300 seconds.

    -   For the agent value, specify the amount of time to wait for the agent to install. If you specify a value for the `agent_timeout` property on the `IBM::UrbanCode::SoftwareDeploy::UCD` resource in a blueprint, it replaces the agent value.
    -   For the component\_process value, specify the total amount of time to allow for all the component deployment processes to complete. If you specify a value for the `component_process_timeout` property on the `IBM::UrbanCode::SoftwareConfig::UCD` resource in a blueprint, it replaces the component\_process value.
    -   For the ucd\_client value, specify the amount of time to allow for the return of REST API calls from the server. If you specify a value for the `ucd_client_timeout` property on the `IBM::UrbanCode::SoftwareDeploy::UCD` or `IBM::UrbanCode::ResourceTree` resource in a blueprint, it replaces the ucd\_client value.
    -   For the agent\_subgroup value, specify the amount of time to allow for the server to create groups that are attached to an agent. This value is used only if you use the WebSphere® Application Server - Deployment plug-in to locate WebSphere Application Server cells during automatic discovery. To learn more about automatic discovery, see [Importing resources from WebSphere Application Server](../../com.udeploy.doc/topics/resources_import_was.md#).
    -   For the sleep\_delay value, specify the amount of time to delay processes if the agent that runs the process is not connected.

        **Note:** For best processor performance, set this parameter to `10`.

    -   For the application\_process value, specify the amount of time to wait for the agent to complete an application process request. If you specify a value for the `ucd_client_timeout` property on the `IBM::UrbanCode::ApplicationProces::UCD` resource in a blueprint, it replaces the application\_process value.
2.   Update the timeout for your cloud projects. If the sum of the agent and component\_process values is greater than the stack timeout value for a cloud project, you must update the stack timeout.
    1.   Click **Settings** \> **Clouds**. 
    2.   Select a cloud. 
    3.   In the **Timeout in Mins** field, specify the amount of time in minutes to wait for a provision request to be completed. 
    4.   Click **Save**. 

**Parent topic:** [Blueprint design server configuration](../../com.edt.doc/topics/c_node_administering_bds.md)

