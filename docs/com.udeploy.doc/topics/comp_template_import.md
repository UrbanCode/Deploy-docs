# Importing component templates

When you import a template, you can create an entirely new template or upgrade an existing one.

When you export components, applications, processes, or templates, and then import them on a different computer, the same versions of the same plug-ins must be installed on both computers.

1.  Display the Import Template dialog \(**Components** \> **Templates** \> **Import Template**\).
2.   Click **Choose File**, and then select the JSON file that contains the template. 

    **Note:** You must create the JSON file that contains the template on a server that uses the same version of HCL® UrbanCode™ Deploy as the destination server.

3.  If you want to upgrade an existing template, check the **Upgrade Template** check box. To create a template, leave the box cleared.If the template's name in the JSON file \(not the name of the file itself\) matches an existing template, the template is upgraded. If the name is not found, the command has no effect.

    **Note:** The template's name is the first parameter in the JSON file; for example,

    ```
    "name": "helloWorldTemplate",
    ```

4.   In the **Generic Process Update Type** list, specify how to handle generic processes that are being imported along with the component template and that have the same names as existing generic processes. 

    **Note:** This field affects only generic processes, not component template processes.

    -   ****Use Existing Process****

        Select this option to ignore generic processes in the imported component template when those processes have the same name as existing generic processes.

    -   ****Create Process****

        Select this option to rename any generic processes that have the same name as existing processes.

    -   ****Fail If Process Exists****

        Select this option to cancel the import if the imported component template references any generic processes that have the same name as existing generic processes.

    -   ****Fail If Process Does Not Exist****

        Select this option to cancel the import if the imported component template references any generic processes that do not have the same name as existing generic processes.

    -   ****Upgrade If Exists****

        Select this option to update generic processes to match the imported generic processes.

5.  Click **Submit**.

**Parent topic:** [Component templates](../topics/comp_template.md)

