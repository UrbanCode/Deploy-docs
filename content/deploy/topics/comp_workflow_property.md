# Adding process properties {#comp_workflow_property .task}

A process property provides a way to add user-supplied information to a process. A running process can prompt users for information and then incorporate it into the process. For example, if the process entails authenticating with another server, you can require that a user enter an ID and a password for the process to continue. Properties are defined in the Edit Property dialog box.

1.  Open the process.
2.   On the **Configuration** tab, click **Component Process Properties**, **Application Process Properties**, or **Process Properties**, depending on the type of process. The Configuration tab looks like the following figure:

    ![The properties for the process, shown in the Configuration tab for the process](../images/comp_workflow_property_a.gif)

3.   In the Edit Properties dialog box, enter a name in the **Name** field. 
4.  Optionally, enter a description in the **Description** field. 
5.  Enter a label in the **Label** field. The label is associated with the property in the user interface.
6.   In **Pattern**, enter a regular expression to require that user input values for this property match a specific pattern. Leave this field blank to accept any values. 
7.  If the property is required, check the **Required** check box.The default value is that the property is not required.
8.  Specify the type of expected value with the **Type** list. Supported types are: `text`, `text area`, `check box`, `select`, `multi select`, and `secure`. Default type is `text`.
9.  In the **Default Value** field, enter a default value \(if any\).
10. To save your work, click **Save**. To discard changes, click **Cancel**.

To use a property in a process, reference it when you configure \(see [Component processes](comp_process.md)\) a step that uses it.

**Parent topic:** [Processes](../topics/comp_workflow.md)

