# Property availability {#ud_properties .concept}

The properties that are available to you depends on the context. For example, in a component process, you can access the component properties of the current component. In an application process, you can access the application properties and environment properties, but not any component properties. The following table shows the processes in which each type of property is available.

To see the properties that are available to a process, run the process. When the process is finished, go to the **Properties** tab of the process request. This tab lists all the properties that are available to the process. The following table lists types of properties that are available to processes and which processes have access to each type of property.

|Property type|Processes that can access the property|Sample syntax|
|-------------|--------------------------------------|-------------|
|Generic process properties|Generic processes|`${p:ProcessProp1}`|
|Application process properties|Application processes and component processes|`${p:ProcessProp1}`|
|Component process properties|Component processes|`${p:ProcessProp1}`|
|Component version properties|Component processes types that include versions, such as Deployment and Operational \(with version\)|`${p:version/VersionProp1}`|
|Resource properties|Component processes and generic processes|`${p:resource/ResourceProp1}`|
|Environment properties|Component processes and application processes|`${p:environment/EnvProp1}`|
|Application properties|Application processes and component processes|`${p:application/AppProp1}`|
|System properties|All processes|`${p:system/SystemProp1}`|
|Request properties|All processes| -   `${p:request.user.id}`
-   `${p:request.user.displayName}`
-   `${p:request.user.name}`

 |
|Iteration properties|Processes in the For Each Agent step context| -   `${p:iteration/agent.name}`
-   `${p:iteration/agent/AGENT_HOME}`

 |
|Agent properties|Generic processes and component processes|`${p:agent/PropName}`|

**Parent topic:** [Properties](../topics/ud_properties_overview.md)

