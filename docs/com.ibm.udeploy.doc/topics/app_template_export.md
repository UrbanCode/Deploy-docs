# Exporting application templates

Exporting a template creates a JSON file \(file extension .json\) that contains the template's configuration information, resource templates, environment templates, approval processes, application processes, and generic processes.

To move application templates between servers, you can export the template and import it on a different server. When you import an application template, all resource templates, environment templates, approval processes, application processes, generic processes, and tags that it uses are also imported.

When you export components, applications, processes, or templates, and then import them on a different computer, the same versions of the same plug-ins must be installed on both computers.

**Note:** Exporting application templates in this way includes only the most recent version of each embedded application process.

For information about JSON, see [the JSON website](http://www.json.org/).

1.   Go to the Application Templates pane \(**Applications** \> **Templates**\). 
2.   In the same row as the application template to export, click **Actions** \> **Export**. In the default download location for your browser, a file with the same name as the application template is saved. For example, if the application is named JPetStore, the JSON file is named JPetStore.json.

You can import the application to another server that uses the same version of HCL® UrbanCode™ Deploy. See [Importing application templates](app_template_import.md).

**Parent topic:** [Application templates](../topics/app_template.md)

