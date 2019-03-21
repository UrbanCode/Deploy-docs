# Property contexts

Properties are available in various contexts. Not all properties are available for all contexts. To plan and set properties, you must know where to access properties and how that setting behaves in context.

The following table shows the contexts in which properties are available and how you can use the properties.

**Tip:** The context that you set a property in can have narrow or widespread influence. For example, if you set a system property, that property persists in all areas. The key to setting properties effectively is to find a balance to setting narrowly as possible without setting them so narrow that you create extra work for yourself.

|**Example: Overriding server locations**Consider this example: Initially you have one Tomcat server. To store the location of that server, you create an application property with the name `Tomcat.server.url` and the location of that server. Your environments refer to that property to know where the Tomcat server is.

Then, suppose that you add a second Tomcat server. This Tomcat server is intended for use only by specific environments. So on those specific environments, you create an environment property with the same name `Tomcat.server.url` and the location of the second server.

Now the environment has two properties with the same name: one system property and one environment property. The order of precedence determines which property value is used. Environment properties come before system properties in the order of precedence. Therefore, the environment uses the value of the environment property instead of the system property. In this way, you can use system properties to set defaults and then you can override those properties in specific contexts.

|

The following table shows the order of precedence of properties.

|Context|Description|
|-------|-----------|
|Process| Available on the **Configuration** tab of the process, whether it is a generic process, application process, or component process.

 Reference syntax: $\{p:propertyName\}.

 |
|Component version| Available on the component **Configuration** tab. Click **Component** \> **selected component** \> **Configuration** \> **Version Property Definitions**. Then, specify values on individual component versions.

 Referenced: $\{p:version/propertyName\}.

 |
|Resource| Available on the resource **Configuration** tab. Click **Resources** \> **selected resource** \> **Configuration** \> **Resource Properties**.

 Referenced: $\{p:resource/propertyName\}.

 You can also use the following syntax to get a comma-separated list of all properties: `${p:resource/allProperties}`.

 |
|Agent|Available on the agent **Configuration** tab. Click **Resources** \> **Agents** \> **selected agent** \> **Configuration** \> **Agent properties**.Referenced: `${p:agent/propertyName}`.

In a For Each Agent context, you can use the following syntax to get a comma-separated list of all properties: `${p:iteration/allProperties}`.

|
|Environment| Environment properties are available on the **Configuration** tab for environments. Also, components can have component environment properties; these properties transfer to the environment when the component is deployed. An environment property overrides the value that is set on a component environment property that has the same name.

 Reference syntax: `${p:environment/propertyName}`.

 You can also use the following syntax to get a comma-separated list of all properties: `${p:environment/allProperties}`.

 Both the component and environment properties use the same syntax.

 For example, assume that you are deploying a web application to three environments. Each environment might have the application server in a different location. You can specify this location in an environment property on each environment.

 |
|Component| Available on the component **Configuration** tab. Click **Component** \> **selected component** \> **Configuration** \> **Component Properties**.

 Referenced: `${p:component/propertyName}`.

 You can also use the following syntax to get a comma-separated list of all properties: `${p:component/allProperties}`.

 |
|Application| Available on the application **Properties** tab. Click **Applications** \> **selected application** \> **Configuration** \> **Application Properties**.

 Reference syntax: `${p:application/propertyName}`.

 |
|System| System \(global\) properties are available on the **Settings** tab. Click **Settings** \> **Properties**.

 Reference syntax: `${p:system/propertyName}`.

 The system property is broadest. If you plan to deploy an application, use application properties because it's more specific.

 If you have an `xyz` system property and an `xyz` application property, and you want to use the value of the system property, you must provide the entire context. Otherwise, the value resolves to the application property.

 You can also use the following syntax to get a comma-separated list of all properties: `${p:system/allProperties}`.

 |

