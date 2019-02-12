# Referring to properties

HCL® UrbanCode™ Deploy provides several ways to refer to properties.

## Referring to properties

Properties can be referred to by scope or without scope. The scope is the type of artifact that contains the property, such as the environment or component. You refer to a property by scope this way:

```
${p:scope/propertyName}
```

You refer to a property without scope this way:

```
${p:propertyName}
```

For example, if you create an environment variable that is named UAT, you can refer to it this way:

```
${p:environment/UAT}
```

You can refer to the same environment variable without scope this way:

```
${p:UAT}
```

In the same way, you can refer to many types of properties, such as application properties, system properties, and resource properties.

**Warning:** In some cases, you can refer to a property without the `p:` prefix, such as in the code `${myProperty}`. This method for referring to properties is deprecated and should not be used. Referring to properties in this way can conflict with shell script variables or other values.

Use the `?` syntax if you are not sure about a property name:

```
${p?:propertyName}
```

This syntax returns a blank if the property is not found, and avoids the undefined property error.

## Properties in application processes and component processes

When you create or edit process steps for applications and components, you can use the autocomplete feature to determine which properties are available in a particular context. When you are editing an input field for a process step, if you type $\{p:, a list of the available property scopes is displayed. Select a scope from the list. The list of all available properties in that scope is then displayed. Select the property to use from the list.

## Secure properties

When you create a property, you can specify whether it is secure. Secure properties are stored in encrypted form. Secure properties are encrypted with an Advanced Encryption Standard \(AES\) algorithm and a 128-bit key. Secure properties are displayed in obscured form in the user interface.

If you create a custom plug-in that uses secure properties, the property value is displayed in obscured form in the user interface. For example, if your plug-in prints the property value to standard output and you examine the standard output in the user interface, the property value is displayed in obscured form.

If your custom plug-in writes the property value to a file, then the property value is not obscured.

**Note:** Use strong and complex values for secure properties. Because the secure property value is obscured in the output log, any other text that matches the secure property value is also obscured.

## Property order of precedence

If a property is defined in multiple places, its value is determined by the property order of precedence. The following list defines the order of precedence from highest to lowest:

|Process|
|Component version|
|Resource|
|Agent|
|Environment|
|Component|
|Application|
|System|

If you have an environment property that is named `${p:environment/db.hostname}` and a resource property with the same name, you can refer to the resource property by using `${p:db.hostname}` or `${p:resource/db.hostname}`. Because the resource property is higher on the order of precedence than the environment property, in this case you must refer to the environment property by using the scoped format: `${p:environment/db.hostname}`.

|**Example: Overriding server locations**Consider this example: Initially you have one Tomcat server. To store the location of that server, you create an application property with the name `Tomcat.server.url` and the location of that server. Your environments refer to that property to know where the Tomcat server is.

Then, suppose that you add a second Tomcat server. This Tomcat server is intended for use only by specific environments. So on those specific environments, you create an environment property with the same name `Tomcat.server.url` and the location of the second server.

Now the environment has two properties with the same name: one system property and one environment property. The order of precedence determines which property value is used. Environment properties come before system properties in the order of precedence. Therefore, the environment uses the value of the environment property instead of the system property. In this way, you can use system properties to set defaults and then you can override those properties in specific contexts.

|

|**Example: Defining properties in a step**Consider a process that defines properties in a step.

In this example, create a component process with a **Replace Tokens** step. Edit the step to reference a property list, using the **Property List** field. When the process runs, the normal order of precedence is not used. Instead, the order of properties in the property list is used to replace the tokens.

|

## Setting multiple component properties by environment

When components share a property, you can save time by setting the property value on the environment instead of setting it on every component. To use this feature:

1.  Click **Components** \> **selected component** \> **Configuration** \> **Environment Property Definitions**.
2.  On the Environment Property Definitions page, define the property.
3.  Repeat the process for each effected component.
4.  On the environment that uses the components, click **Configuration** \> **Environment Properties** \> **Set a Single Value**.
5.  Set the property value.

## Component version properties

Properties can be defined for component versions. Each version can have a unique property value. To use this feature:

1.  Click **Components** \> **selected component** \> **Configuration** \> **Version Property Definitions**.
2.  On the Version Property Definitions page, define the property. By default, this value is applied to every version that is created for this component.
3.  To override a component version property with a unique value, click **Configuration** \> **Version Properties** for the version.
4.  Set the property value.

## Using the ? wildcard in property references

The question mark character, `?`, can be used to reference properties. The syntax is:

```
${p?:propertyName}
```

For example:

```
${p?:agent/wsadmin.path}
```

returns the value of the property if it exists, otherwise it returns an empty string.

## Escaped characters

HCL UrbanCode Deploy escapes the following characters:

```

\
=
,
```

Replace "\\" with "\\\\"; "=" with "\\="; and "," with "\\,".

**Parent topic:** [Properties](../topics/ud_properties_overview.md)

