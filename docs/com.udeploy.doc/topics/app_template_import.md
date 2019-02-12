# Importing application templates

If you exported an application template, you can import the template to a different server. When you import an application template, you can create an entirely new template or upgrade an existing one.

To move application templates between servers, you export the templates and import them to a different server.

When you export components, applications, processes, or templates, and then import them on a different computer, the same versions of the same plug-ins must be installed on both computers.

**Note:** You must create the JSON file that contains a template on a server that uses the same version of HCL® UrbanCode™ Deploy as the destination server.

When you import an application template, all resource templates, environment templates, approval processes, application processes, generic processes, and tags that it uses are also imported.

1.   Open the Import Application Template dialog box by clicking **Applications** \> **Templates** \> **Import Application Template**. 
2.   Click **Choose File**, and then select the name of the JSON file that contains the template. 
3.   To upgrade an existing application template, select **Upgrade Template**. To create a template, leave **Upgrade Template** cleared. If the name of the application template in the JSON file \(not the name of the file itself\) matches an existing template name, then the template parameters are upgraded. If items such as processes or properties exist, new versions are created. New items, such as processes, environment templates, resource templates, or properties, are also added. If the name of the application template is not found, the import action has no effect.

    **Note:** The application template name is the first parameter in the JSON file. The following example shows the first parameter in the JSON file:

    ```
    "name": "JPetStore",
    ```

4.   If the application template's processes contain generic processes, use the **Generic Process Upgrade Type** list to specify how the generic processes that are called in the application processes are upgraded or created. This selection affects only generic processes, not the application processes in the application template. The import process has different results depending on whether the generic processes exist.

    **Note:** The server tracks generic processes by name. If a generic process on the destination server is assigned the same name as a generic process that is imported, then the generic process exists on the server.

    -   To import an application template without updating the generic processes that are on your server, select **Use Existing Generic Process**. If the generic process does not exist, a generic process is created. If a generic process with that name exists, another version is not created.
    -   To create generic processes, select **Create Generic Process**. A copy of the generic process is always created. If a generic process with that name exists, a unique string is added to the new generic process's name. When run, the application process calls the new generic process.
    -   To create a fresh installation and ensure that generic processes are not on the importing server, select **Fail if Generic Process Exists**. If you are creating an application template, it creates both an application template and generic processes unless generic processes exist, in which case the import action fails.

        If you are upgrading an application template, the upgrade fails if the imported application template's generic processes exist.

    -   To ensure that generic processes are on the importing server, select **Fail if Generic Process Does Not Exist**. If you are creating an application template, it creates both the application template and generic processes, unless the generic processes do not exist, in which case the import action fails.
    -   To upgrade the generic processes, select **Upgrade if Generic Process Exists**. This option creates an application template and versions of the generic processes on the importing server. If the generic processes do not exist, processes are created.
5.   In the **Resource Template Upgrade Type** list, specify how to handle resource templates that are being imported, along with the application templates that have the same names as existing resource templates. 
    -   To import an application template without updating the resource templates that are on your server, select **Use Existing Resource Template**. If the resource templates do not exist, resource templates are created. If a resource template with that name exists, another version is not created.
    -   To create resource templates, select **Create Resource Template**. Copies of the resource templates are always created. If a resource template with that name exists, a unique string is added to the new resource template's name. When run, the application process calls the new resource template.
    -   To create a fresh installation and ensure that resource templates are not on the importing server, select **Fail If Resource Template Exists**. If you are creating an application template, it creates both the application template and resource templates unless resource templates exist, in which case the import action fails.

        If you are upgrading an application template, the upgrade fails if the imported application template's resource templates exist.

    -   To ensure that resource templates are on the importing server, select **Fail If Resource Template Does Not Exist**. If you are creating an application template, it creates both the application template and resource templates unless the resource templates do not exist, in which case the import action fails.
    -   To upgrade the resource templates, select **Upgrade Resource Template If Exists**. This option creates an application template and versions of the resource templates on the importing server. If the resource templates do not exist, resource templates are created.
6.   Click **Submit**. 

**Parent topic:** [Application templates](../topics/app_template.md)

