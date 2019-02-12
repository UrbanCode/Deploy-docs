# Converting TOSCA files to blueprints for the blueprint designer

You can convert Topology and Orchestration Specification for Cloud Applications \(TOSCA\) files to the HOT format and import them into the blueprint designer.

Create a TOSCA template that describes your cloud environment. The TOSCA template format standardizes how a web application is deployed, including the ability to specify artifacts.

**Note:** You must use absolute paths to any resources that are used in the TOSCA template.

1.   In the blueprint editor of the blueprint designer, click **New**. 
2.   In the Add a New File window, specify a name and description for the blueprint. 
3.   If your workspace contains multiple repositories, select a project from the **Repository** list. If your workspace contains a single repository, the **Repository** list is not displayed.
4.   In the **Type** list, select **Blueprint**. 
5.   From the **Clone** list, select **Clipboard or File**. 
6.   Provide the TOSCA file to the blueprint designer by using one of the following steps. 
    -   Paste the entire TOSCA template into the template field.
    -   Click **Choose File**, select the TOSCA file, and then click **Open**. The file name is displayed in the Add a New File window.
7.   In the **Translator** field, specify the conversion service to use. To use IBM's TOSCA to HOT converter that is hosted on Bluemix®, enter this URL: `http://tosca-translator.mybluemix.net/tosca/v1.0/translate` 
8.   Click **Save**. The new blueprint opens in the editor. Any conversion errors are listed at the top of the blueprint. If you use the converter that is hosted on Bluemix, the errors contain both an error name and explanation, as shown in the following text:

    ```
    UnknownFieldError: Template contains unknown field "descriptions". Refer to the definition to verify valid values.
    ```

    Since conversion errors might prevent you from provisioning your blueprint, you must review the blueprint before you provision it.


-   You can modify the contents of the blueprint. See [Creating files with the blueprint designer](blueprint_edit.md#).
-   You can provision environments from the blueprint. See [Provisioning environments from the blueprint designer \(through OpenStack Heat\)](env_provision_edt.md#).

**Parent topic:** [Editing blueprints with the blueprint designer](../../com.edt.doc/topics/blueprint_create.md)

