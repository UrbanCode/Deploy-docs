# Creating application templates

Define application templates so that users can create applications that contain the types of components, the environments, and the resource tree that you specify.

1.   Click **Applications** \> **Templates** \> **Create Application Template**. 
2.   Define the application template: 
    1.   Enter a name and description, and select the teams that can access the application template. 
    2.   From the **Notification Scheme** list, select a notification scheme. 
    3.   To require that a version be provided for each component when a snapshot is created, select **Enforce Complete Snapshots**. 
    4.   To set the tags that components must use to be assigned to an application during creation, select tags from the **Required Component Tags** list. You specify the minimum, maximum, or exact number of components that contain the tag that the user must select. 

        **Note:** 

        By selecting component tags, you limit only the components that a user can assign to an application during its creation. If they have permission, users can add other components to an application after they exit the wizard.

    5.   Click **Save**. 
3.   Define application properties. The application properties that you define are included in all applications that use this application template.
    1.   Click **Configuration**. This **Configuration** tab is associated with the application template that you created, not the main **Configuration** tab. 
    2.   Click **Application Property Definitions**. 
    3.   Click **Add Property**, define the property, and click **Save**. 
4.   Create an application process. The application process that you define is included in all applications that use this application template.
    1.   Click **Processes**. This **Processes** tab is associated with the application template that you created, not the main **Processes** tab. 
    2.   Click **Create Process** to open the Create an Application Process dialog box, and create the application process. See [Creating application processes](app_process_create.md). 
    3.   Edit the process in the process editor. See [Editing processes](comp_workflow_edit.md). 

        **Note:** In the process editor, you can select only a limited number of process steps, such as the **Install Multiple Components** and **Run Operational Process for Multiple Components** steps.

5.   Create environment templates. The environments that you define can be used by all applications that use this application template. When applications are created from application templates, multiple environments can be created from each environment template. You must assign a resource template to an environment template. See [Creating environment templates](app_environment_template_create.md#).

    **Note:** To minimize additional steps after you create an application from this template, ensure that the resource template that you select specifies both agent prototypes and the component tags that you selected.

    **Note:** If you create an environment with an environment template and then add component mappings to the resource template used by the template, the new component mappings are added to the environment. However, if you remove component mappings from the resource template, the component mappings are not removed from the environment.

6.   Create environment gates. The environments gates that you define must be used by all applications that use this application template and cannot be removed from these applications. See [Creating environment gates](app_gate_create.md).

By using team object mapping, grant the team access to application template, agents, component instances, component templates, environment templates, and resource templates. See [Mapping teams to objects](../../com.udeploy.admin.doc/topics/security_teams_mapping.md).

**Parent topic:** [Application templates](../topics/app_template.md)

