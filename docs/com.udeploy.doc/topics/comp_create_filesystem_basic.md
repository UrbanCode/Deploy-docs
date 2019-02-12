# Creating components from a nonversioned file system

To import artifacts that are not stored in versioned folders, store the artifacts in a folder and create a component with the **File System** source configuration type.

When you use this type of component, you must manually create versions. To create versions of components automatically, see [Creating components from a versioned file system](comp_create_filesystem_versioned.md).

1.   In HCL® UrbanCode™ Deploy, click **Components**, and then click **Create Component**. 
2.   In the Create Component window, specify a name and description for the component. 
3.  In the **Teams** fields, specify the access information for the new component.
4.  To use a template for the new component, select a template from the **Template** list. In this case, the component inherits source configuration, properties, and processes from the template. For information about templates, see [Component templates](comp_template.md).
5.   In the **Source Configuration Type** list, select **File System**. 
6.  Specify the following parameters for the component: 
    -   ****Base Path****

        Specify the path to the directory that contains the artifacts.

    -   ****Always Use Name Pattern****

        If you select this check box, new versions are automatically named according to the pattern in the **Version Name Pattern** field. If you clear this check box, you must specify a name each time you create a version.

    -   ****Version Name Pattern****

        Specify a pattern for each version name. You can use the $\{version\} variable to include an automatically incremented version number. For example, by using the `mycomp_${version}` pattern, the server produces versions such as `mycomp_1` and `mycomp_2`.

        This parameter is meaningful only if you select the **Always Use Name Pattern** check box.

    -   ****Next Version Number****

        Specify the version number for the next version.

        This parameter is meaningful only if you select the **Always Use Name Pattern** check box.

    -   ****Extensions of files to Convert****

        If text-type files must be converted into another character set, type the list of file extensions to be converted. Matching file types are converted into the default or system character set of the system where the agent is located. Separate list items with commas, for example:

        ```
        txt,log,ini,sh
        ```

    -   ****Import Versions Automatically****

        This parameter has no effect on this source configuration type. You must import new versions manually.

    -   ****Copy to CodeStation****

        This option, which is selected by default, creates tamper-protected copies of the artifacts and stores them in the embedded artifact management system, CodeStation. If the check box is cleared, only metadata about the artifacts is imported. In most cases, keep this check box selected. The default for this setting is in the system setting **Components copy to CodeStation by default**; see [Server settings](../../com.udeploy.admin.doc/topics/settings_system.md).

    -   ****Default Version Type****

        Specify how to import versions into CodeStation:

        -   ****Full****

            Each version is comprehensive and contains all artifacts.

        -   ****Incremental****

            Each version contains a subset of artifacts.

    -   ****Use the system's default version import agent/tag****

        If this parameter is selected, the agent or tag that you specified on the System Settings page is used to import component artifacts. Agents must have access to the system where the artifacts are located. See [Server settings](../../com.udeploy.admin.doc/topics/settings_system.md)

    -   ****Import new component versions using a single agent****

        If this parameter is selected, use the **Agent for Version Imports** field to identify the agent that is used to import artifacts into the component. The agent must have access to the system where the artifacts are located. To import artifacts from where the server is located, install an agent in the same location and specify that agent.

    -   ****Import new component versions using any agent with the specified tag****

        If this parameter is selected, use the **Agent Tag for Version Imports** field to identify the tag that is used to select agents to import artifacts into the component. All tagged agents must have access to the system where the artifacts are located.

    -   ****Use Default Artifact Cleanup Settings****

        To apply the component version cleanup settings that are specified on the System Settings page, select the **Use Default Artifact Cleanup Settings** check box. If this check box is cleared, you must specify how long to keep component versions. For more information about cleaning up component versions, see [Cleaning up component versions](settings_system_preview.md).

    -   ****Run Process after a Version is Created****

        To automatically run a process after versions are imported, select this check box, and then specify an application process and an environment for the process. The process runs only when the version is imported automatically, not when you import versions manually. Similarly, the process does not run when you create versions with the REST API or the `udclient` command. If the automatic version import finds multiple versions, the process runs only once.

7.   Click **Save**. The new component is included in the list of components.
8.   Import the first version of the component: 

    1.   Go to the **Versions** tab. 
    2.   Click **Import New Versions**. 
    3.   Specify a name for the new version and then click **Save**. 
    The new version is included in the list of versions. You can confirm that the artifacts are included in the version by clicking the version and looking at the list of artifacts.

9.  To import future versions of the component, click **Import New Versions** again and specify a name for the new version. 

The new component is listed on the Components page. The Versions tab shows the available versions of the component.

Create processes for the component. See [Creating component processes](comp_process_configure.md).

**Parent topic:** [Creating components from the file system](../topics/comp_create_filesystem.md)

