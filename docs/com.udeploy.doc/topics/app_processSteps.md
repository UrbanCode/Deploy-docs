# Process steps: Reference

Application processes, component processes, and generic processes are created with the process editor.

HCL® UrbanCode™ Deploy provides several common process steps. Otherwise, application processes are assembled from processes that are defined for their associated components. Application processes, like component processes, are created with the process editor.

The following process steps are provided by the server. For information about steps that are provided by plug-ins, see the documentation for the individual plug-in on IBM® developerWorks®: [IBM UrbanCode™ Deploy Plug-ins](https://developer.ibm.com/urbancode/plugins/ibm-urbancode-deploy).

-   **[Acquire lock](../topics/app_processsteps_lock_acquire.md)**  
This step acquires a lock on a specified string value. You can use locks to prevent concurrent modification of resources.
-   **[Add Inventory Status](../topics/comp_process_add_inv_stat.md)**  
With this process step, the component resource that the process is running against will have an inventory entry created for it with the specified status.
-   **[Apply Configuration](../topics/app_processsteps_apply_config.md)**  
This step runs a component process of the type Operational \(No Version Needed\) or Configuration Deployment.
-   **[Apply to Live Configuration](../topics/app_process_apply_live_config.md)**  
This step is a wrapper step for applying configuration updates to an application server.
-   **[Compare with Live Configuration](../topics/app_process_compare_live_config.md)**  
This step is a wrapper step for comparing the configuration of an HCL UrbanCode Deploy resource to a live application server.
-   **[Finish](../topics/app_processsteps_finish.md)**  
Ends processing. A process can have more than one Finish step. All processes must reach a Finish step to complete successfully.
-   **[For Each Agent](../topics/app_process_every_agent.md)**  
This step creates a loop that iterates over the agents in the environment.
-   **[For Each Tag](../topics/app_process_every_tag.md)**  
This step iterates over resource tags in application processes.
-   **[Install Component](../topics/app_processsteps_install.md)**  
This step installs the selected component with one of the processes that are defined for the component.
-   **[Install Multiple Components](../topics/app_process_multiple_comps.md)**  
Install multiple components that are based on component tags or resource tags.
-   **[Inventory Update](../topics/app_process_inventory_update.md)**  
This step updates the inventory and compliance for the environment.
-   **[Join](../topics/app_processsteps_join.md)**  
The Join step merges a process so that only one step runs at a time. If any of the steps that connect to a Join step fail or do not run, the Join step causes the process to fail.
-   **[Manual Application Task \(Utility\)](../topics/app_processsteps_manual_generic.md)**  
A manual task interrupts an application process until manual intervention is done. A task-interrupted process remains suspended until the targeted user or users respond. Typically, manual tasks are removed after the process is tested or automated.
-   **[Note](../topics/app_processsteps_note.md)**  
The Note step adds a note to a process diagram.
-   **[Operational component processes](../topics/app_processsteps_operational.md)**  
Runs the specified operational \(no version needed\) component process.
-   **[Release lock](../topics/app_processsteps_lock_release.md)**  
This step releases a lock on a specified string value.
-   **[Remove Inventory Status](../topics/comp_process_remove_inv_stat.md)**  
With this process step, the component resource that the process is running against will have an inventory entry removed from it.
-   **[Rollback Component](../topics/app_processsteps_rollback.md)**  
Use this process step to roll back a component version to the version in a snapshot or to the version that was deployed when the process began.
-   **[Rollback Multiple Components](../topics/app_process_rollback_multi.md)**  
Use this step to roll back multiple component versions to versions in a snapshot or to versions that were deployed when the process began. The multiple components are based on component tags or resource tags.
-   **[Run Component Process](../topics/comp_process_run_comp_procss.md)**  
You can run a component process as a part of a step.
-   **[Run Generic Process](../topics/app_processsteps_generic_process.md)**  
This step runs a generic process as a step in an application process.
-   **[Run Generic Process for Each Affected Resource](../topics/app_processsteps_run_process_resource.md)**  
Runs the specified generic process on each resource that is affected by the application process.
-   **[Run Operational Process for Multiple Components](../topics/app_processsteps_run_operational.md)**  
Runs the operational \(no version needed\) process for multiple components.
-   **[Run Process for Each Version](../topics/app_processsteps_run_process_version.md)**  
Use this step to run the specified process once for each version of the specified component.
-   **[Set Status](../topics/app_processsteps_set_status.md)**  
This step sets the ending status of the process. The step can specify that the process is completed or failed.
-   **[Switch](../topics/app_processsteps_switch.md)**  
Use this step to create branches in the process that are based on the value of a property.
-   **[Uninstall Component](../topics/app_processsteps_uninstall.md)**  
Use this step to uninstall the selected component.
-   **[Uninstall Multiple Components](../topics/app_processs_uninst_multi_cmpnts.md)**  
Use this step to uninstall multiple components that are based on component tags or resource tags.
-   **[Update from Live Configuration](../topics/app_process_upgrade_live_config.md)**  
This step is a wrapper step for updating a resource with the configuration information from an application server.

**Parent topic:** [Processes](../topics/comp_workflow.md)

