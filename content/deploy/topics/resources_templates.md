# Resource templates {#resources_templates .concept}

A resource template is a model for a group of resources. The template contains a hierarchy of resources, groups, and agent prototypes that is a starting point for creating new resources.

Resource templates contain agent prototypes, which represent agents that are not yet installed or connected to an environment. When you create an environment, you can use a resource template as a model for the environment. Then, you can map real agents to the agent prototypes in the template.

Resource templates provide a pattern for an environment. For example, you can use resource templates to represent dynamic cloud environments. See [Importing resource templates from clouds](resources_template_import_cloud.md). If you define environment templates in an application template, you must use resource templates to define the resource models for the environment templates. See [Creating application templates](app_template_create.md#).

**Note:** If you create an environment with an environment template and then add component mappings to the resource template used by the template, the new component mappings are added to the environment. However, if you remove component mappings from the resource template, the component mappings are not removed from the environment.

-   **[Creating resource templates](../topics/resources_templates_create.md)**  
To create a resource template, specify the contents and organization of the template, including resources, groups, and agent prototypes.
-   **[Defining a new template from the resource tree](../topics/resources_define_template.md)**  
You can create a resource template from an existing resource group in the resource tree.

**Parent topic:** [Resources](../topics/resources_ch.md)

