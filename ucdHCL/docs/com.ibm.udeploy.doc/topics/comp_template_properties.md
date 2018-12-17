# Component template properties

Component template properties ensure that every component created from a template has the same properties. The types of available properties are described in the following table.

|Type|Description|
|----|-----------|
|Properties|Custom property. Every component inherits the value that is defined in the template \(it cannot be overridden by a component\). If you change the value, the change is reflected in components that are created from the template, including components that were previously created.|
|Component Property Definitions|Every component has this property. It appears on the Create Component dialog box for every component that is created from this template \(see [Creating components](comp_create.md)\). A value that is defined here can be changed by created components.|
|Environment Property Definitions|Every environment that uses a component that is created by this template has this property. The property appears on the environment's Component Mappings pane \(**Applications** \> **selected application** \> **Environments** \> **selected environment** \> **Component Mappings**\), see [Application environments](app_environment.md). A value that is defined here can be changed by environment.|
|Resource Property Definitions|This property appears on resources that the component is deployed to.|

**Parent topic:** [Component templates](../topics/comp_template.md)

