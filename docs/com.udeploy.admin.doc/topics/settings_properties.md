# System properties

System properties are global variables for the server.

System properties are available on the **Settings** tab: click **Settings** \> **Properties**.

References to system properties are similar to the following example:

```
${p:system/propertyName}
```

If you create a `SUCCESS`system variable , for example, you would refer to it as in the following example:

```
echo ${p:system/SUCCESS}
```

Output in this case:

```
SUCCESS
```

**Parent topic:** [Managing security](../../com.udeploy.admin.doc/topics/security_ch.md)

**Parent topic:** [Properties](../../com.udeploy.doc/topics/ud_properties_overview.md)

