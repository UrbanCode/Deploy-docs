# Creating components from Rational Asset Manager {#comp_create_ram .task}

IBM® Rational® Asset Manager is a library management system for creating and governing software assets.

Install an agent that has access to the IBM Rational Asset Manager server.

To learn more about Rational Asset Manager, see [Rational Asset Manager ](http://www-01.ibm.com/support/knowledgecenter/SSUS84_7.5.2/com.ibm.ram.web.nav.doc/helpindex_ram.html?cp=SSUS84_7.5.2%2F0).

1.   In IBM UrbanCode® Deploy, click **Components**, and then click **Create Component**. 
2.   In the Create Component window, specify a name and description for the component. 
3.  In the **Teams** fields, specify the access information for the new component.
4.  To use a template for the new component, select a template from the **Template** list. In this case, the component inherits source configuration, properties, and processes from the template. For information about templates, see [Component templates](comp_template.md).
5.   In the **Source Configuration Type** list, select **Rational Asset Manager**. 
6.  Specify the following parameters for the component: 

     **Repository URL**
     :   The location of the Rational Asset Manager repository. To find the repository URL, log on to Rational Asset Manager from a web browser. Click **Help** \> **Extensions**. The repository URL is displayed in the **Repository location** field, such as the following example:

        ```
        http://ram.example.com:9080/ram
        ```

      **User**
     :   The Rational Asset Manager user name.

      **Password**
     :   The password that is associated with the Rational Asset Manager user name.

      **Unique ID**
     :   The ID, or GUID, of the Rational Asset Manager asset to load as a component source. In Rational Asset Manager, the ID of an asset is displayed in the Attributes section of the General Details page for the asset.

      **Version Pattern**
     :   A regular expression that represents the version of the Rational Asset Manager asset to load as a component source. For example, \(1\\.\[0-9\]+\).\* matches versions such as `1.2` and `1.2.3.4A`. If the expression matches more than one version, all versions are imported, up to the number in the **Latest Build Count** field.

      **State**
     :   The state of the Rational Asset Manager asset to load as a component source. Specify a value to limit the component to only assets with the specified state.

        States are defined in lifecycles in Rational Asset Manager. To learn more about lifecycles, see [Asset development and lifecycles](http://www-01.ibm.com/support/knowledgecenter/SSUS84_7.5.2/com.ibm.ram.doc/topics/c_asset_lifecycle.html) in the Rational Asset Manager documentation.

      **Query**
     :   The query to use to select an asset to load. Use this field only if you want to specify the asset with a complex query.

      **Latest Build Count**
     :   The number of the search results to load. By default, only the most applicable result is loaded. However, to load more than one version or state of the asset, specify the number to load.

      **Extensions of files to Convert**
     :   If text-type files must be converted into another character set, type the list of file extensions to be converted. Matching file types are converted into the default or system character set of the system where the agent is located. Separate list items with commas, for example:

        ```
        txt,log,ini,sh
        ```

      Charset
     :   If file types are listed in the **Extensions of files to Convert** field, specify the character set to use. Otherwise, the file types are converted into the default or system character set of the system where the agent is located.

      **Include Dependent**
     :   Select to load the related assets that the asset depends on.

      **Preserve Execute Permissions**
     :   For Linux™ and UNIX™ operating systems, select this check box to retain the execute permissions for each file.

      **Preserve Execute Permissions**
     :   For Linux and UNIX operating systems, select this check box to retain the execute permissions for each file.

      **Import Versions Automatically**
     :   Select this check box to check for new versions periodically and to import new versions automatically. Also, if you select this check box, the server synchronizes the status of the component with the state of the asset.

        If you do not import versions automatically, you can import versions manually by clicking **Components** \> **selected component** \> **Versions** and then clicking **Import New Versions**.

      **Copy to CodeStation**
     :   This option, which is selected by default, creates tamper-protected copies of the artifacts and stores them in the embedded artifact management system, CodeStation. If the check box is cleared, only metadata about the artifacts is imported. In most cases, keep this check box selected. The default for this setting is in the system setting **Components copy to CodeStation by default**; see [Server settings](../../com.ibm.udeploy.admin.doc/topics/settings_system.md).

      **Default Version Type**
     :   Specify how to import versions into CodeStation:

         **Full**
         :   Each version is comprehensive and contains all artifacts.

          **Incremental**
         :   Each version contains a subset of artifacts.

       **Use the system's default version import agent/tag**
     :   If this parameter is selected, the agent or tag that you specified on the System Settings page is used to import component artifacts. Agents must have access to the system where the artifacts are located. See [Server settings](../../com.ibm.udeploy.admin.doc/topics/settings_system.md)

      **Import new component versions using a single agent**
     :   If this parameter is selected, use the **Agent for Version Imports** field to identify the agent that is used to import artifacts into the component. The agent must have access to the system where the artifacts are located. To import artifacts from where the server is located, install an agent in the same location and specify that agent.

      **Import new component versions using any agent with the specified tag**
     :   If this parameter is selected, use the **Agent Tag for Version Imports** field to identify the tag that is used to select agents to import artifacts into the component. All tagged agents must have access to the system where the artifacts are located.

      **Use Default Artifact Cleanup Settings**
     :   To apply the component version cleanup settings that are specified on the System Settings page, select the **Use Default Artifact Cleanup Settings** check box. If this check box is cleared, you must specify how long to keep component versions. For more information about cleaning up component versions, see [Cleaning up component versions](settings_system_preview.md).

      **Run Process after a Version is Created**
     :   To automatically run a process after versions are imported, select this check box, and then specify an application process and an environment for the process. The process runs only when the version is imported automatically, not when you import versions manually. Similarly, the process does not run when you create versions with the REST API or the `udclient` command. If the automatic version import finds multiple versions, the process runs only once.

 7.  Click **Save**.

The new component is listed on the Components page. The Versions tab shows the available versions of the component. If you selected the **Import Versions Automatically** check box, versions are displayed automatically. Otherwise, click **Import New Versions** to show the available versions. Depending on the number and size of the artifacts, it might take time before the versions are displayed. To see the artifacts in the component, click a component version.

Create processes for the component. See [Creating component processes](comp_process_configure.md).

**Parent topic:** [Creating components from source-code management systems](../topics/comp_create_scm.md)

