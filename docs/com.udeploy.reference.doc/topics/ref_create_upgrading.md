# Upgrading plug-ins

This example shows how to upgrade a plug-in.

To create an upgrade, first, increment the number of the `version` attribute of the `<identifier>` element in the plugin.xml file. Next, update the property and step-type elements in the plugin.xml file.

If you change the names of a step or property, you must create an upgrade.xml file that contains the changes. Add a `<migrate>` element in the upgrade.xml file with a `to-version` attribute that contains the new number. Finally, place the names of changed property and step-type elements that match the updated plugin.xml file in this element, as shown in the following example:

```
<?xml version="1.0" encoding="UTF-8"?>
<plugin-upgrade
        xmlns="http://www.&company;.com/UpgradeXMLSchema_v1"
        xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <migrate to-version="3">
    <migrate-command name="Run SQLPlus script">
      <migrate-properties>
        <migrate-property name="sqlFiles" old="sqlFile"/>
      </migrate-properties>
    </migrate-command>
  </migrate>
</plugin-upgrade>
```

You can also make a script-only upgrade, which is an upgrade that contains changes to the step's associated scripts and files but does not change the plugin.xml file. This mechanism can be useful for plug-in development and for minor bug-fixes and updates.

If an update to a plug-in removes functionality, such as removing a step property, you must upgrade the plug-in and then open and re-save any processes that use the step. Until you open and re-save the processes, they use the pre-upgrade steps.

When creating a new version of a plugin, you many change the value of server:sub-tag in plugin.xml, and you do not need to add an entry to upgrade.xml for the change to take effect.

**Parent topic:** [Creating plug-ins](../../com.udeploy.reference.doc/topics/reference_plugins_create.md)

