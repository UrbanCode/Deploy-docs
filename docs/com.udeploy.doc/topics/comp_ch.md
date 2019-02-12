# Components

Components represent deployable items along with user-defined processes that operate on them, usually by deploying them.

Understanding components is critical to understanding HCL® UrbanCode™ Deploy.

Deployable items, or artifacts, can be files, images, databases, configuration materials, or anything else that is associated with a software project. Artifacts can come from a number of sources: file systems, build servers such as IBM® Anthill Pro, source version control systems, Maven repositories, and many others. When you create a component, you identify the source and define how the artifacts are brought into HCL UrbanCode Deploy. If the source is Subversion, for example, you specify the Subversion repository that contains the artifacts. Each component represents artifacts from a single source.

Components have component processes. A component process is a series of user-defined steps that operate on the component or its artifacts. Each component has at least one process and can have several. A component process can be as simple as a single step or contain numerous relationships, branches, and process switches. Component processes are created with the process editor. The process editor is a visual drag-and-drop editor that lets you drag process steps onto the design space and configure them as you go. As more steps are placed, you visually define their relationships with one another. Process steps are selected from a menu of standardized steps. HCL UrbanCode Deploy provides steps for several utility processes, such as inventory management, and workflow control. More process steps are provided by plug-ins. A component process can have steps from more than one plug-in. See [Plug-ins](../../com.udeploy.reference.doc/topics/plugin_ch.md).

After you define the source and processes for a component, you import its artifacts into the artifact repository, CodeStation. Artifacts can be imported automatically or manually. By default, a complete copy of the content is imported into CodeStation \(the original artifacts are untouched\). Each time a component is imported, including the first time, it is versioned. Versions can be assigned automatically by HCL UrbanCode Deploy, applied manually, or come from a build server. Every time the artifacts are modified and reimported, a new version of the component is created. Components have versions, which are used to ensure that the appropriate component instances get deployed.

Additionally, you can create processes and configure properties and save them as templates to create components. See [Component templates](comp_template.md).

-   **[Creating components](../topics/comp_create.md)**  
In general, component creation is the same for all components.
-   **[Component processes](../topics/comp_process.md)**  
A component process is a series of user-defined steps that operate on a component's artifacts.
-   **[Component versions](../topics/comp_version.md)**  
Each time a component's artifacts are imported into the repository, including the first time, a separate version is stored in CodeStation. Versions can be assigned automatically by HCL UrbanCode Deploy, applied manually, or come from a build server.
-   **[Component properties](../topics/comp_properties.md)**  
Components can have several types of properties. The server keeps track of changes to component properties as property versions.
-   **[Creating component manual tasks](../topics/comp_tasks_create.md)**  
A component manual task interrupts a component process until manual intervention is done. To create a component manual task, add a manual step to a component process, and select a notification template.
-   **[Component templates](../topics/comp_template.md)**  
With a component template, you can save and reuse component processes and properties and create components from them; template-based components inherit the template's properties and process.
-   **[Component change logs](../topics/comp_changeLog.md)**  
Change logs provide information about modifications to components.
-   **[Deleting components](../topics/comp_del.md)**  
When a component is deleted, it is removed from the database and CodeStation and cannot be activated later.

**Parent topic:** [Modeling software deployment](../topics/part_using.md)

