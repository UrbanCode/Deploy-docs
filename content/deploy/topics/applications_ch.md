# Applications {#applications_ch .concept}

Applications are responsible for bringing together all the components that must be deployed together.

Applications do this task by defining the different versions of each component and defining the different environments that the components must go through on the way to production. In addition, applications also map the constituent hosts and systems \(called resources\) that a component needs within every environment.

Applications also implement automated deployments, rollbacks, and similar tasks. These tasks are called processes. However, at the application level, processes are concerned only with the components and resources that are necessary for deployment, and related tasks. By contrast, component processes are concerned with running commands and related tasks.\).

Applications also introduce snapshots to manage the different versions of each component. A snapshot represents the current state of an application in the environment. Typically, the snapshot is generated in an environment that has no approval gates. This type of environment is called an uncontrolled environment. For most users, the snapshot is pushed through the pipeline.

**Note:** Before you configure an application, install at least one agent in a target environment. For evaluation purposes, the agent can be on the same system as the server. In addition, you must also add at least one resource group to the agent. See [Resources](resources_ch.md).

## Environments { .section}

An environment is a collection of resources that host the application. Environments typically include host systems and IBM UrbanCode Deploy agents. When a deployment is run, it is always done so in an environment. While environments are collections of resources, resources can vary per environment.

For example, environment 1 might include a single web server, a single middleware server, and a single database server. IBM UrbanCode Deploy represents these systems as three separate resources that are running in environment 1. Environment 2, however, might include several clustered databases and servers. To deploy the same components on these different environments, IBM UrbanCode Deploy organizes the resource elements with resource groups. The server also keeps an inventory of everything that is deployed to each environment. In this way, the IBM UrbanCode Deploy server manages the contents of each environment and tracks the differences between those environments.

## Processes { .section}

A process plays a coordination role. They are authored with a visual drag-and-drop editor, and composed of steps that call the component processes. For example, to deploy the application you might run a process that is called Deploy. This Deploy process would in turn run the requisite components and run the deployment.

## Snapshots { .section}

Snapshots specify what combination of component versions you deploy together. They are models that you create before you deploy the application. A snapshot specifies the exact version for each component in the application. When a snapshot is created, IBM UrbanCode Deploy gathers together information about the application, including the component versions, for an environment. Typically, the snapshot is generated in an environment that has no approval gates. This kind of environment is called an uncontrolled environment. For most users, the snapshot is pushed through the pipeline. Typically, one of the environments remains uncontrolled to allow for snapshots. When a successful deployment runs in the uncontrolled environment, a snapshot is created based on the state of the application within the environment: thus capturing the different versions of the components at that time. As the application moves through various testing environments, for example, IBM UrbanCode Deploy ensures that the exact versions \(bit for bit\) are used in every environment. After all the appropriate stages and approvals for a snapshot are complete, the snapshot is pushed to production.

-   **[Getting started with creating applications](../topics/getstart_application_create.md)**  
Applications associate resources with environments and define processes to run deployments.
-   **[Creating applications](../topics/app_create.md)**  
You can create an application from scratch or import an existing one.
-   **[Building and deploying mobile applications](../topics/plugins_worklight_buildanddeploy.md)**  
You can set up your development environment so that you can build your mobile applications and, by using the IBM MobileFirst Platform Foundation \(formerly Worklight®\) plug-in forIBM UrbanCode Deploy, deploy the build results to the MobileFirst Platform Foundation Server.
-   **[Application environments](../topics/app_environment.md)**  
An environment is a user-defined collection of resources that hosts an application.
-   **[Application templates](../topics/app_template.md)**  
With an application template, you can save and reuse a collection of resources, environments, processes, and tagged components or component templates to create a standardized application.
-   **[Application processes](../topics/appl_processes_intro.md)**  
Application processes, like component processes, are created with the process editor. You use application processes to deploy or to roll back components.
-   **[Application blueprints](../topics/app_blueprint.md)**  
An application blueprint maps application components to a resource template. When you create an environment or provision one from the cloud, you can use the blueprint as a model.
-   **[Snapshots](../topics/app_snapshot.md)**  
A snapshot is a collection of specific versions of components and processes. Typically, a snapshot represents a set of component versions that are known to work together. In most cases, snapshots include all of the components in an application.
-   **[Creating manual application tasks](../topics/app_tasks_creating.md)**  
A manual application task interrupts an application process until manual intervention is done. To create a manual task, add a manual step to an application process and select a notification template.
-   **[Approval process](../topics/app_approvalCreate.md)**  
An approval process specifies the job that needs approval and the role of the approver.

**Parent topic:** [Modeling software deployment](../topics/part_using.md)

