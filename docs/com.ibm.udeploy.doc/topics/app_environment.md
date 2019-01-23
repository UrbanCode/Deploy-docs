# Application environments

An environment is a user-defined collection of resources that hosts an application.

An environment is the application's mechanism for bringing together components with the agent that deploys them. Environments are typically modeled on some stage of the software project lifecycle, such as development, QA, or production. A resource is a deployment target, such as a database or Java™ Platform, Enterprise Edition container. Usually, resources are found on the same host where the agent that manages them is located. A host can be a physical system, virtual machine, or be cloud-based.

Environments can have different topologies, for example: an environment can consist of a single server; be spread over several servers; or spread over clusters of servers. Environments are assigned to specific applications. Although multi-tenant systems can be the target of multiple applications, most IT organizations use application-specific environments. Additionally, approvals can be assigned to specific environments.

HCL® UrbanCode™ Deploy maintains an inventory of every artifact that is deployed to each environment and tracks the differences between them.

Environment properties can be created with the environment's Properties pane \(**Applications** \> **selected application** \> **Environments** \> **selected environment** \> **Properties**\).

A value that is set on a component environment property overrides an environment property that has the same name.

Referenced: `${p:environment/propertyName}`.

-   **[Creating environments](../topics/app_environment_create.md)**  
Before you can run a deployment, you must define at least one application environment that associates components with an agent on the target host.
-   **[Creating environments from WebSphere Application Server cells](../topics/examples_websphere_import_cell.md)**  
You can import information about a WebSphere® Application Server cell into resources and then use those resources in an environment.
-   **[Creating environment gates](../topics/app_gate_create.md)**  
To create an environment gate, specify the conditions that must be met before component versions can be deployed to the environment.
-   **[Mapping resources and components to environments](../topics/app_environment_mapping.md)**  
Specify where components are deployed by adding a resource or resource group to the environment. Then, map the components to those resources.
-   **[Comparing environments](../topics/app_environment_compare.md)**  
You can compare two environments to see differences in their inventories or property values.

**Parent topic:** [Applications](../topics/applications_ch.md)

