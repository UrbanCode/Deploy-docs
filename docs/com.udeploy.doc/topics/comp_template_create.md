# Creating component templates

To create a component template, specify information about the template, such as which plug-in it is related to.

1.  To create a template:
2.   Display the Create Component Template dialog box \(**Components** \> **Templates** \> **Create Template**\). 

    ![The Create Component Template window](../images/comp_template_create_a.gif)

3.  Enter the template's name in the **Name** field. 
4.   Enter a description in the **Description** field. The description can be used to convey more information about the template.
5.  In the **Teams** fields, specify the access information for the template.
6.  In the **Component Type** list, select **z/OS** for System z® components and **Standard** for all other components.
7.   In the **Source Configuration Type** list, select the source type of the component. Selecting a value other than the default `None`, displays more fields that are associated with your selection. Source-dependent fields are used to identify and configure the artifacts. If you select a source, components that are based on the template use the same source.

    For information about creating components of specific types, see [Creating components from the file system](comp_create_filesystem.md), [Creating components from build integration tools](comp_create_buildTools.md), or [Creating components from source-code management systems](comp_create_scm.md).

    **Note:** 

    If you select a source, any properties you configure are set for any components that are created with the template.

8.  Click **Save** to save the template. Saved templates are listed in the Component Templates pane.
9.  Add components, processes, and properties to the template. 

**Parent topic:** [Component templates](../topics/comp_template.md)

