# Modeling software deployment

Modeling software deployment in HCL® UrbanCode™ Deploy includes configuring components and component processes and adding those components to applications. Then, you use processes to deploy the components to environments.

The general steps in this typical workflow include:

1.  Import the parts of the application as components. See [Creating components](comp_create.md).
2.  Create processes that deploy components. See [Component processes](comp_process.md).
3.  Create an application to group the components together. See [Applications](applications_ch.md).
4.  Create an application process that runs each component process. See [Creating application processes](app_process_create.md).
5.  Create one or more environments on which to deploy the components. See [Creating environments](app_environment_create.md).
6.  Run the application process to deploy the components. See [Deploying applications](deployment_ch.md).
7.  Take snapshots of working deployments so you can save these arrangements and deploy them to other environments. See [Creating snapshots](app_snapshot_create.md).

The following diagram illustrates this workflow:

![A diagram that shows the basic workflow of using HCL UrbanCode Deploy](../images/part_using_a.gif)

-   **[Components](../topics/comp_ch.md)**  
Components represent deployable items along with user-defined processes that operate on them, usually by deploying them.
-   **[Resources](../topics/resources_ch.md)**  
A resource is a logical deployment target that typically resolves to an agent and a user-defined construct that is based on the architectural model of HCL UrbanCode Deploy.
-   **[Applications](../topics/applications_ch.md)**  
Applications are responsible for bringing together all the components that must be deployed together.
-   **[Inventories](../topics/inventory_ch.md)**  
You use different inventories to track installed components and properties in HCL UrbanCode Deploy elements.
-   **[Processes](../topics/comp_workflow.md)**  
Processes are automated tasks that run on agents.
-   **[Statuses](../topics/comp_version_status.md)**  
Create and apply statuses to track component inventory states or to track component versions in environments and resources.
-   **[Properties](../topics/ud_properties_overview.md)**  
Properties are variables that store information about many different elements, including components, environments, processes, and applications. You can also set global properties for the system.
-   **[Tags](../topics/tags_ch.md)**  
A tag is a user-defined, shared, short label that you use to classify, view, and conduct operations on objects such as applications, components, agents, and resources.

