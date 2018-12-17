# Component properties

Components can have several types of properties. The server keeps track of changes to component properties as property versions.

To define component properties, click the **Components** tab, click the component, and then go to the **Configuration** tab. The following table describes the types of properties that are available on components.

|Type|Description|
|----|-----------|
|Component properties| Component properties are values that are assigned on individual components.

 Referenced: `${p:component/propertyName}`.

 |
|Component properties that are inherited from component templates| Components inherit properties from component templates. These properties cannot be changed on the component.

 Referenced: `${p:component/template/propertyName}`.

 |
|Component environment properties| Component environment properties are defined on components. However, the property value is not set until the component is deployed to an environment. In this way, a component environment property can have a different value for each deployed instance of the component.

 However, a value that is set on a component environment property does not override an environment property that has the same name. The environment property has precedence over the component environment property.

 Referenced: `${p:environment/propertyName}`.

 |
|Component version properties| Component version properties are defined on components. However, the property value is not set until a component version is created. In this way, a component version property can have a different value for each component version.

 Referenced: `${p:version/propertyName}`.

 |
|Component resource properties| Component resource properties are defined on components. However, the property value is not set until you map a component to an environment and create a component resource. The property value is set on this component resource. In this way, if you need to deploy multiple copies of a component to the same environment, you can set a different property value for each copy.

 Component resource properties also generate resource roles on the component resources.

 Referenced: `${p:resource/propertyName}`.

 |
|Component property definitions|Aside from component template properties that become component properties, component templates can also have custom properties. These properties appear on the component **Basic Settings** tab. Referenced: `${p:component/custom/propertyName}`.

|

**Parent topic:** [Components](../topics/comp_ch.md)

