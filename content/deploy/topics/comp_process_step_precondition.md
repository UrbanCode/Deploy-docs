# Process step preconditions {#comp_process_step_precondition .concept}

Most steps in a process can have a precondition. If the **Precondition** field is available, the process supports a precondition. This precondition determines whether the step runs. Like post-processing scripts, preconditions use JavaScript™ 1.7.

**Note:** The syntax for preconditions is similar to the syntax for post-processing scripts. See [Post-processing scripts](comp_postProcess.md).

Preconditions return Boolean values. If the precondition returns `True`, the step runs as usual.

If the precondition returns anything other than `True`, the process skips that step. In the process request, the step is labeled "Precondition Failed." However, in this case, the process continues to run; the process follows the success links from that step as though the step succeeded.

The precondition has access to the same properties that the step does. Application processes have access to the following properties:

-   Application properties
-   Application process properties
-   Environment properties, including component environment properties
-   System properties
-   Output properties from previous steps. See [Output properties](output_properties.md).

Property availability depends on your context. See [Property availability](ud_properties_avail.md) for information about which properties you can access.

After you run a process, you can see the properties that the process had access to by opening the process request and clicking the **Properties** tab.

To access a property, use the properties.get\(\) command. For example, the following code retrieves the value of an application property:

```
properties.get("application/property1")
```

The following example precondition allows the step to run only if the application property `property1` exists and is not null:

```
properties.get("application/property1") !== undefined && 
properties.get("application/property1") !== null && 
properties.get("application/property1") !== ""
```

**Important:** Do not use notation such as `${p:component.myProperty}` in the precondition script. For example, to check the value of a component property in a component process, use `properties.get("myProperty") == "myValue"`.

Precondition scripts can access the process properties. For example, if the process has a property that is named `processProperty1`, you can access that property with the following code:

```
properties.get("processProperty1")
```

Precondition scripts in component processes and generic processes can access the output properties of previous steps. For example, assume that the post-processing script of a step that is named `Step1` specifies a property that is named `OutputProp1`. The following precondition script allows another step to run only if the value of this property is `value1`:

```
properties.get("Step1/OutputProp1") == "value1"
```

Preconditions have access to a property that is named `hasFailures`. This property is `True` if any of the steps in the process fail. It is undefined if no steps fail. For example, to run a step only if no other steps in the process fail, use the following precondition:

```
properties.get('hasFailures') == undefined
```

**Parent topic:** [Process step types and logic](../topics/process_steps.md)

