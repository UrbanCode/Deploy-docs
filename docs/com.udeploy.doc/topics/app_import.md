# Importing applications

If you exported an application, you can import the application on a different server. When you import an application, you can create an entirely new application or upgrade an existing one.

To move applications between servers, you export the applications and import them to a different server.

**Note:** You must create the JSON file that contains an application on a server that uses the same version of HCL® UrbanCode™ Deploy as the destination server.

When you import an application, components and other items that are associated with the application are also imported, including their properties and processes \(if they are available to the importing server\).

**Note:** Notification schemes are not imported.

When you import an application, components and other items that are associated with the application are also imported, including their properties and processes \(if they are available to the importing server\).

When you export components, applications, processes, or templates, and then import them on a different computer, the same versions of the same plug-ins must be installed on both computers.

For information about templates that are associated with imported components, see [Importing components](comp_import.md).

**Notes:** 

-   If imported components have the Import Versions Automatically parameter set to true, HCL UrbanCode Deploy automatically imports component versions if the artifacts are accessible to the importing server.
-   You might receive an error message that indicates the Java™ heap space is out of memory when you attempt to import an application. To resolve the issue, increase the Java heap size. Open the server\_directory/bin/set\_env file, and set the Java heap size to a higher value, such as 2 GB.


To share applications that have secured properties among IBM® UrbanCode™ Deploy servers, exchange keys from each server's encryption keystore. Refer to [Sharing secured properties among servers](../../com.udeploy.install.doc/topics/ssl_mutual_authServers.md#)

1.  Open the Import Applications dialog box by clicking **Applications** \> **Import Applications**.
2.   Click **Choose File**, and then select the name of the JSON file that contains the application definition. 

    **Note:** You must create the JSON file that contains the application definition on a server that uses the same version of HCL UrbanCode Deploy as the destination server.

3.   To upgrade an existing application, select **Upgrade Application**. To create an application, leave **Upgrade Application** cleared. If the name of the application in the JSON file \(not the name of the file itself\) matches an existing application name, then the application parameters are updated. If items such as processes or properties exist, new versions are created. New items, such as processes, environments, components, or properties, are also added. If the name of the application is not found, the import action has no effect.

    **Note:** The application name is the first parameter in the JSON file. This example shows the first parameter in the JSON file:

    ```
    "name": "helloWorldApplication",
    ```

4.   Configure how to import the items that are associated with the application. When you import an application, all application templates, components, generic processes, and resource templates that are associated with the application are also imported. For each item type, you must select the option from the list that determines how each item type is imported or upgraded. If your application does not contain items of a type, accept the default value.

    -   ****Application Template Upgrade Type****

        If the application was created from an application template, you must specify how to import the application template.

    -   ****Component Upgrade Type****

        If the application contains components, you must specify how to import them.

        **Note:** The components must be on the importing server.

    -   ****Generic Process Upgrade Type****

        If the application processes contain generic processes, you must specify how to import them. If you are also upgrading components, then the generic processes that are called in the component processes are also affected. The import process has different results if the generic processes exist or not.

        **Note:** The server tracks generic processes by name. If a generic process on the server is assigned the same name as a generic process that is imported, then the generic process exists on the server.

    -   ****Resource Template Upgrade Type****

        The application template might also contain resource templates. Specify how to import resource templates that have the same names as existing resource templates.

    | | |
    |--|--|
    |**Use Existing Item Type**|To use the same item that is used by the imported application, select this option. The new application contains references to the item.If you are upgrading, the application uses the imported item.

|
    |**Create Item Type**|To create an item that is based on the item that the imported application uses, select this option. A new item is created that is based on the item of the imported application. If you are upgrading, the application uses the newly created item, and it no longer uses the item that it previously used.

|
    |**Fail If Item Type Exists**|When you want to create a fresh installation, select this option. If you are creating an application, HCL UrbanCode Deploy creates both a new application and item unless the item exists, in which case the application is not imported.If you are upgrading, the upgrade fails if the item exists on the importing server.

|
    |**Fail If Item Type Does Not Exist**|To ensure that an item is on the importing server, select this option. If you are creating an application, HCL UrbanCode Deploy creates both a new application and item unless the item does not exist, in which case the application is not imported. If you are upgrading, the upgrade fails if the imported item does not exist on the importing server.

|
    |**Upgrade Item Type If Exists**|To upgrade the existing item, select this option. This option creates an application and upgrades the existing item with data from the imported application. If you are upgrading and an existing item matches an imported one, the item is upgraded. If the imported item matches the existing one, the imported item is used.

|

5.  Click **Submit**.

