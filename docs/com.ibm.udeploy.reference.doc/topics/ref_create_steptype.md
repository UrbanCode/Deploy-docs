# Plug-in steps: The `step-type` element

You define plug-in steps with the `step-type` element; each `step-type` element represents a single step in the HCL® UrbanCode™ Deploy process editor.

A `step-type` element has a name attribute and up to four child elements:

-   `description`
-   `properties`
-   `command`
-   `post-processing`

The mandatory name attribute identifies the step. The description and name are shown in the web application and on informational pages for the plug-in. The contents of the description determine which icon is displayed with the step.

```
<step-type name="Start">
<description>Start Apache HTTP server</description>

```

**Note:** A step name cannot contain the forward slash \(/\) character.

-   **[Step properties: the properties element](../../com.ibm.udeploy.reference.doc/topics/ref_create_properties.md)**  
The `properties` element is a container for properties, which are defined with the `property` tag.
-   **[Plug-in step icons](../../com.ibm.udeploy.reference.doc/topics/ref_create_icons.md)**  
A keyword in the description determines which icon is displayed in the plug-in step.

**Parent topic:** [Creating plug-ins](../../com.ibm.udeploy.reference.doc/topics/reference_plugins_create.md)

