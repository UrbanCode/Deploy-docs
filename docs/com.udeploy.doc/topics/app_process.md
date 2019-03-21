# Application processes

You can use application processes to deploy or to roll back components.

HCL® UrbanCode™ Deploy provides several common process steps. Otherwise, application processes are assembled from processes that are defined for their associated components. Application processes, like component processes, are created with the process editor.

Application processes can run manually, automatically on some trigger condition, or on a user-defined schedule. When a component has several processes, the application determines which ones run and in which order. For instance, an n-tiered application might have a web tier, a middleware tier, and a database tier. And, continuing the example, the database tier must be updated before the other two, which are then deployed concurrently. An application can orchestrate the entire process, including putting target servers online and offline for load balancing as required.

An application process is always associated with a target environment. When an application process runs, it interacts with a specific environment. At least one environment must be associated with the application before the process can run. Application processes are independent of environment; processes can be designed independently of any particular environment. These application processes enable a single application to interact with separate environments, such as QA, or production. To use the same application process with multiple environments \(a typical scenario\), you associate each environment with the application and run the process separately for each one.

In addition to deployments, several other common processes are available, such as rolling-back deployments. HCL UrbanCode Deploy tracks the history of each component version, which enables application processes to restore environments to any point.

Application processes and the steps that they comprise are configured with the process editor. For information about using the process editor, see [Processes](comp_workflow.md). For information about individual process steps, see [Process steps: Reference](app_processSteps.md).

