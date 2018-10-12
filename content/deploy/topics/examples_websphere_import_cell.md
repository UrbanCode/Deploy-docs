# Creating environments from WebSphere Application Server cells {#examples_websphere_import_cell .task}

You can import information about a WebSphere® Application Server cell into resources and then use those resources in an environment.

You must have a WebSphere Application Server cell and an application in the IBM® UrbanCode® Deploy server.

1.  Import resources from the WebSphere Application Server cell as described in [Importing resources from WebSphere Application Server](resources_import_was.md).When you are finished, you have a collection of resources that represent the cell and the nodes, servers, and other artifacts in the cell. These resources are under the agent resource for the WebSphere Application Server system.
2.  In the IBM UrbanCode Deploy server, create an application environment.
3.  Add the resources to the environment: 
    1.  Open the environment and go to the **Resources** tab. 
    2.  Click **Add Base Resources**. 
    3.  Select the agent resource and click **OK**. 

Now you can run application processes on the environment, including processes that contain steps in the WebSphere Application Server - Deploy plug-in.

**Parent topic:** [Application environments](../topics/app_environment.md)

