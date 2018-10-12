# Application processes {#app_processes_intro .concept}

Application processes, like component processes, are created with the process editor. You use application processes to deploy or to roll back components.

**Tip:** For full coverage of application processes, see [Application processes](app_process.md) and its subtopics.

IBM® UrbanCode® Deploy provides several common process steps. Otherwise, application processes are assembled from processes that are defined for their associated components.

Application processes can run manually, automatically on some trigger condition, or on a user-defined schedule. When a component has several processes, the application determines which ones run and in which order. For instance, an n-tiered application might have a web tier, a middleware tier, and a database tier. And, continuing the example, the database tier must be updated before the other two, which are then deployed concurrently. An application can orchestrate the entire process, including putting target servers online and offline for load balancing as required.

**Parent topic:** [Applications](../topics/applications_ch.md)

