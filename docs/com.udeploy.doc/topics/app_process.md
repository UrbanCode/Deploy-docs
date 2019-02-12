# Application processes

You can use application processes to deploy or to roll back components.

HCL® UrbanCode™ Deploy provides several common process steps. Otherwise, application processes are assembled from processes that are defined for their associated components. Application processes, like component processes, are created with the process editor.

Application processes can run manually, automatically on some trigger condition, or on a user-defined schedule. When a component has several processes, the application determines which ones run and in which order. For instance, an n-tiered application might have a web tier, a middleware tier, and a database tier. And, continuing the example, the database tier must be updated before the other two, which are then deployed concurrently. An application can orchestrate the entire process, including putting target servers online and offline for load balancing as required.

An application process is always associated with a target environment. When an application process runs, it interacts with a specific environment. At least one environment must be associated with the application before the process can run. Application processes are independent of environment; processes can be designed independently of any particular environment. These application processes enable a single application to interact with separate environments, such as QA, or production. To use the same application process with multiple environments \(a typical scenario\), you associate each environment with the application and run the process separately for each one.

In addition to deployments, several other common processes are available, such as rolling-back deployments. HCL UrbanCode Deploy tracks the history of each component version, which enables application processes to restore environments to any point.

Application processes and the steps that they comprise are configured with the process editor. For information about using the process editor, see [Processes](comp_workflow.md). For information about individual process steps, see [Process steps: Reference](app_processSteps.md).

-   **[Creating application processes](../topics/app_process_create.md)**  
You can use application processes to deploy or to roll back components.
-   **[Deploying components in an application process](../topics/app_process_deploy_comp.md)**  
You can deploy one or more components in an application process by calling component processes.
-   **[Running application processes](../topics/app_process_run.md)**  
To run an application process, specify the environment to use and the process to run. In many cases, you also specify the component versions to deploy.
-   **[Running the same process again](../topics/deployapp_repeatrequest.md)**  
The repeat request function is available after an application deployment completes. The **Repeat Request** feature is on the Process Request page for the application.
-   **[Uninstalling components with an application process](../topics/app_process_deploy_uninstall.md)**  
You can uninstall components by using an Uninstall Component step in an application process.
-   **[Rolling back to a snapshot](../topics/app_process_deploy_rollback.md)**  
You can roll back a component to the versions that are in a snapshot. In this case, you use a **Rollback Component** step with the **Remove Undesired Incremental Versions** option.
-   **[Rolling back components that fail to deploy](../topics/app_process_deploy_rollback_last.md)**  
If an application process fails to deploy a component, you can add a rollback step to the process to reverse the deployment. In this case, you use the **Replace with Last Deployed** option.
-   **[Modeling blue-green, rolling, and canary deployments](../topics/app_process_advanced_ov.md)**  
The For Each Agent and For Each Tag steps provide ways to deploy to large environments in stages, allowing you to run flexible blue-green or rolling deployments, with or without updating canary nodes first.

**Parent topic:** [Processes](../topics/comp_workflow.md)

