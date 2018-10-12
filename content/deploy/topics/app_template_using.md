# Creating applications from application templates {#app_template_using .task}

Create an application from a template to apply a set of tagged components, environments, and the specified resource tree to the application.

Confirm that your role has access to an application template and the permissions that are needed to create an application from a template. See [Permissions reference for using application templates](../../com.ibm.udeploy.admin.doc/topics/app_template_ref.md#).

1.   Click **Applications**, and then click **Create Application**. 
2.   Complete the information in the Create Application dialog box. See [Creating applications](app_create.md).

    **Note:** You must select the application template from the **Application Template** list.

3.   If the application template specifies application properties, you must complete them. Application properties are listed at the bottom of the dialog box, after the **Enforce Complete Snapshots** option.

    **Note:** You cannot delete application properties that you create with the application template. After you create the application, you can view and edit these properties. Open the application, click the **Configuration** tab \(not the Configuration tab at the top of the page\), and then click **Basic Settings**.

4.   Click **Next**. 
5.   Select components from the appropriate lists or create components to satisfy the listed requirements. You must select or create the number of components that is specified for each tag type.

    **Note:** To create components, you must have permission to create components from templates. You can only create components from component templates that contain the tag that is specified in the application template.

6.   Click **Next**. 
7.   Create the environments to use in this application. By default, one environment is shown for each environment template in the application template. You can create more environments that use the same template or remove any environments, including those environments provided by default.

    -   To create another environment, click **Create an environment from a template** ![](../images/add_app_temp.gif), and then select the environment from the list. An environment is added to the **Environment list**. The environment name contains the name of the environment template and a unique number.
    -   To create a copy of an environment, select the environment and click **Duplicate the selected environment** ![](../images/copy_app_temp.gif). An environment is added to the **Environment list**. The environment name contains the name of the source environment name and "copy." The new environment contains the same values for the description and properties values as the source environment.
    -   To remove an environment, select the environment from the Environments list, and then click **Delete the selected environment** ![](../images/delete_app_temp.gif).
    **Note:** You cannot delete environment properties that you create with the application template. After you create the application, you can view and edit these properties. Open the environment, click the **Configuration** tab \(not the Configuration tab at the top of the page\), and then click **Basic Settings**.

8.   If an environment template contains environment properties, provide values for them. You must provide values for required environment properties. If an environment contains required properties, a blank circle is displayed in the same row as the environment name. When all required environment properties are provided, the circle is shaded.
9.   Click **Next**. 
10.  If you specified environment templates, add agents to them. Drag an agent onto each agent prototype that is shown in the Environments pane. If you drag multiple agents onto an agent prototype, a copy of the resource tree for the agent prototype is created for each agent.
11.  Click **Save**. 

**Parent topic:** [Application templates](../topics/app_template.md)

