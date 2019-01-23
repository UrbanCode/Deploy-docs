# Retrieving property values from external files

You can specify that a property takes a value from an XML or JSON file over HTTP. Then, when you run the process, the server prompts you with a list of values from that file.

On a computer that is accessible from the HCL® UrbanCode™ Deploy, host an XML or JSON file that contains the values for the property. You can format this file in several different ways. You must also identify the path to the values with three parameters. Examples of these path parameters are included with the example files.

The simplest way to format the file is to provide a simple list of values for the property, as in the following examples:

```
<company>
  <employee>Alice</employee>
  <employee>Bob</employee>
  <employee>Chris</employee>
<company>
```

For XML files, you use XPath to specify the path to the values. In the previous XML file, the Base Path parameter is the XPath expression `//company/employee` and parameters Value Path and Label Path are blank.

The following example shows the equivalent file in JSON:

```
{
  company: {
    employee: [
      "Alice",
      "Bob",
      "Chris"
    ]
  }
}
```

In the previous JSON file, the Base Path parameter is `company.employee` and parameters Value Path and Label Path are blank.

You can include separate label and value information in the file. For example, the following XML file includes names and ID numbers.

```
<company>
  <employee>
    <name>Alice</name>
    <id>1</id>
  </employee>
  <employee>
    <name>Bob</name>
    <id>2</id>
  </employee>
  <employee>
    <name>Chris</name>
    <id>3</id>
  </employee>
</company>
```

In this case, the Base Path parameter is the XPath expression `//company/employee`. The Value Path parameter is an XPath expression that shows the path to the value relative to the base path; in this case the expression is `./id`. Similarly, the Label Path parameter an XPath expression that shows the path to the label relative to the base path; in this case the expression is `./name`.

The following JSON file is equivalent to the previous XML file:

```
{
  company: {
    employees: [
      { name: "Alice", employee.id: 1 },
      { name: "Bob", employee.id: 2 },
      { name: "Chris", employee.id: 3}
    ]
  }
} 
```

In this case, the Base Path parameter is `company.employees`. The Value Path parameter is `employee\.id` and the Label Path parameter is `name`.

**Note:** When specify the path for a JSON file, escape periods in attribute names with backslashes, as in the Value Path parameter in the previous example.

When you use attributes in an XML file, use the `@` character to specify an attribute in XPath. For example, the following XML file has values in attributes:

```
<company>
  <employee id="1">Alice</employee>
  <employee id="2">Bob</employee>
  <employee id="3">Chris</employee>
<company>
```

In this case, the Base Path parameter is the XPath expression `//company/employee`. The Value Path parameter is `./@id` and the Label Path parameter is a period \(`.`\).

You can use these remote property values in property definitions, such as component environment properties, but not in general properties such as system properties, application properties, or component properties.

1.  Create a property definition.For example, click a component, go to the **Configuration** tab, click **Environment Property Definitions**, and click **Add Property**.
2.  Specify the **Name**, **Description**, **Label**, **Pattern**, and **Required** fields as usual.
3.  In the **Type** list, select **HTTP Select** for a single property value or select **HTTP Multi Select** to allow multiple property values. Several new fields appear.
4.  Specify the following fields.These fields are specific to parameters from external files.
    -   ****URL****

        Specify the URL of the external XML or JSON file.

    -   ****Username****

        If the URL requires a user name, specify it here.

    -   ****Password****

        If the URL requires a password, specify it here.

    -   ****Data Format****

        Specify the type of file: **JSON** or **XML**.

    -   ****Base Path****

        For XML files, specify an XPath expression to the data. For JSON files, specify the path through the JSON attributes to the data, separating paths with periods \(`.`\). See the examples at the top of this page.

    -   ****Value Path****

        Specify the path to the parameter values, relative to the **Base Path** parameter.

    -   ****Label Path****

        Specify the path to the parameter labels, relative to the **Base Path** parameter.

    -   ****Default Value****

        Specify the default value for the parameter.

5.  Click **Save**.

Now when you run the process, the Run Process window includes a parameter that retrieves values from the external file.

**Parent topic:** [Creating, setting, and editing properties](../topics/resources_properties.md)

