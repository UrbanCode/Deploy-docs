# Step properties: the `properties` element

The `properties` element is a container for properties, which are defined with the `property` tag.

Each step has a single `properties` element; a `properties` element can contain any number of `property` child elements.

A `property` tag has a mandatory `name` attribute, optional `required` attribute, and two child elements, `property-ui` and `value`, which are defined in the following table.

| `<property>` Child Elements|Description|
|----------------------------|-----------|
|`<property-ui>` |Defines how the property is presented to users in the HCL® UrbanCode™ Deploy editor. This element has several attributes: -   `label`

Identifies the property in the editor's Edit Properties dialog box.

-   `description`

Text that is displayed to users in the associated roll-over help box.

-   `default-value`

Property value that is displayed when the Edit Properties dialog box is displayed; used if unchanged.

-   `type`

Identifies the type of widget that is displayed to users. Possible values are:

    -   `textBox`

Enables users to enter an arbitrary amount of text, limited to 4064 characters.

    -   `textAreaBox`

Enables users to enter an arbitrary amount of text \(larger input area than textBox\), limited to limited to 4064 characters.

    -   `secureBox`

Used for passwords. Similar to textBox except values are redacted.

    -   `checkBox`

Displays a check box. If checked, a value of true is used; otherwise the property is not set.

    -   `selectBox`

Requires a list of one or more values, which are displayed in a list. Configuring a value is described below.


 |
|`<value>` |Used to specify values for a selectBox. Each value has a mandatory `label` attribute, which is displayed to users, and a value that is used by the property when selected. Values are displayed in the order they are defined.|

Here is a sample `<property>` definition:

```
<property name="onerror" required="true">
  <property-ui type="selectBox"
    default-value="abort"
    description="Action to perform when statement fails: continue, stop, abort."
    label="Error Handling"/>
  <value label="Abort">abort</value>
  <value label="Continue">continue</value>
  <value label="Stop">stop</value>
</property>

```

**Parent topic:** [Plug-in steps: The step-type element](../../com.ibm.udeploy.reference.doc/topics/ref_create_steptype.md)

