# Application templates {#app_template .concept}

With an application template, you can save and reuse a collection of resources, environments, processes, and tagged components or component templates to create a standardized application.

An application template is a standard framework for users to employ when they create applications. In the application template, you can specify the application properties, environment properties, and environment gates for an application. You can also create a framework that describes attributes of the components, environments, and application processes that an application initially contains. Application templates can contain as many of these elements as required to guide users through the application creation process and to standardize their environments.

 Application and environment properties
 :   You specify which application and environment properties are included in applications that are created from the application template. Users must provide values for these properties when they create an application from the application template, and users cannot remove these properties from the application.

  Environment gates
 :   You specify which statuses a component version must contain before you can deploy it to an environment. The users cannot modify environment gates in environments that were created by using an application template. To add a version status to a component version, see [Adding version statuses](../../com.ibm.udeploy.admin.doc/topics/settings_status_using.md#).

  Components
 :   Instead of identifying which components must be used in the application, you can specify which tags that the components that users assign to the application must use.

    To control which components users can assign to an application by using the template, you must create a naming scheme for component tags that is relevant to your company. You must also consistently apply the tags to components and component templates. See [Adding tags to objects](addingtags_tsk.md#).

    For example, a simple three-tier web application uses a database, web interface, and application logic. You might tag these components with the following tags: `database`, `web_ui`, and `app_logic`. When you create an application template for this web application, you can specify that the application contain three components, one that uses each of those tags. When users create an application from the template, they can assign to the application one component per tag.

  Environments
 :   You can allow users to select environments from the application template. If you do, you must create resource templates that describe the resource tree for each environment. The resource tree can include any agent prototypes, and, if you specify component tags, you can assign the component tags to the agent prototypes. Upon application creation, the components that contain these tags are assigned to the resource tree for the environment. See [Creating resource templates](resources_templates_create.md#).

    **Note:** If you create an environment with an environment template and then add component mappings to the resource template, the new component mappings are added to the environment. However, if you remove component mappings from the resource template, the component mappings are not removed from the environment.

  Application process
 :   You can define a simple application process that installs multiple components. Instead of specifying the component and selecting a process, you specify component tags.

 To ensure that users can create only applications that adhere to templates, you might create a role for users who create applications from templates. See [Creating roles and assigning permissions](../../com.ibm.udeploy.admin.doc/topics/security_roles_create.md). For more information about role permissions that prevent users from modifying applications to deviate from the application templates, see [Application template permissions reference](../../com.ibm.udeploy.admin.doc/topics/app_template_ref.md).

**Note:** If users are granted the certain permissions, they can add or remove components, environments, and application templates after they create an application from the template.

-   **[Creating application templates](../topics/app_template_create.md)**  
Define application templates so that users can create applications that contain the types of components, the environments, and the resource tree that you specify.
-   **[Creating applications from application templates](../topics/app_template_using.md)**  
Create an application from a template to apply a set of tagged components, environments, and the specified resource tree to the application.
-   **[Creating environment templates](../topics/app_environment_template_create.md)**  
When you create an application template, you can define environment templates that model environments for the applications that you create by using the application template.
-   **[Exporting application templates](../topics/app_template_export.md)**  
Exporting a template creates a JSON file \(file extension .json\) that contains the template's configuration information, resource templates, environment templates, approval processes, application processes, and generic processes.
-   **[Importing application templates](../topics/app_template_import.md)**  
If you exported an application template, you can import the template to a different server. When you import an application template, you can create an entirely new template or upgrade an existing one.

**Parent topic:** [Applications](../topics/applications_ch.md)

