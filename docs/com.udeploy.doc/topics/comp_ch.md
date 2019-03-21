# Components

Components represent deployable items along with user-defined processes that operate on them, usually by deploying them.

Understanding components is critical to understanding HCL® UrbanCode™ Deploy.

Deployable items, or artifacts, can be files, images, databases, configuration materials, or anything else that is associated with a software project. Artifacts can come from a number of sources: file systems, build servers such as IBM® Anthill Pro, source version control systems, Maven repositories, and many others. When you create a component, you identify the source and define how the artifacts are brought into HCL UrbanCode Deploy. If the source is Subversion, for example, you specify the Subversion repository that contains the artifacts. Each component represents artifacts from a single source.

Components have component processes. A component process is a series of user-defined steps that operate on the component or its artifacts. Each component has at least one process and can have several. A component process can be as simple as a single step or contain numerous relationships, branches, and process switches. Component processes are created with the process editor. The process editor is a visual drag-and-drop editor that lets you drag process steps onto the design space and configure them as you go. As more steps are placed, you visually define their relationships with one another. Process steps are selected from a menu of standardized steps. HCL UrbanCode Deploy provides steps for several utility processes, such as inventory management, and workflow control. More process steps are provided by plug-ins. A component process can have steps from more than one plug-in. See [Plug-ins](../../com.udeploy.reference.doc/topics/plugin_ch.md).

After you define the source and processes for a component, you import its artifacts into the artifact repository, CodeStation. Artifacts can be imported automatically or manually. By default, a complete copy of the content is imported into CodeStation \(the original artifacts are untouched\). Each time a component is imported, including the first time, it is versioned. Versions can be assigned automatically by HCL UrbanCode Deploy, applied manually, or come from a build server. Every time the artifacts are modified and reimported, a new version of the component is created. Components have versions, which are used to ensure that the appropriate component instances get deployed.

Additionally, you can create processes and configure properties and save them as templates to create components. See [Component templates](comp_template.md).

