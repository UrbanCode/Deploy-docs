# Creating notification templates

Notification templates are the basis for emails that the server sends to users after an event occurs on the server. You can create customized notification templates by modifying the default templates provided, or by creating new templates of your own.

Notification templates are in Apache Velocity format. You can use this format to put together a message template with scripts and parameters that are specified when the notification happens. For example, the template can include information about a process that started, succeeded, or failed. For more information about creating templates with Velocity, see [https://velocity.apache.org/](https://velocity.apache.org/).

Notifications templates are in XML format. The XML references application-specific parameters that are used by Java code to produce the notification email sent to the user. The application-specific parameters that can be used to customize the XML templates are provided in the topic [Parameters for notification templates](notification_params.md).

1.   Duplicate an existing template. Starting in version 6.2.0.2, the application templates are in the folder application\_data/conf/server/notification-templates, where application\_data is the application data folder. The default location is /opt/ibm-ucd/server/appdata/conf/server/notification-templates on Linux™ and C:\\Program Files\\ibm-ucd\\server\\appdata\\conf\\server\\notification-templates on Windows™. In version 6.0 to 6.2.0.1, the templates are in the folder server\_install/conf/server/notification-templates.
2.  Open the new template in a text editor.
3.  In the `<name>` tag, give the new template a unique name.Each template must have a unique name.
4.  In the template, add parameters and other information. 

    To use information from the event that created the notification, use the parameters in [Parameters for notification templates](notification_params.md).

    For example, if you are creating a notification for an application process, you can use the parameter $applicationProcess.getName\(\) to get the name of the process.

    You can also refer to properties just like you can in process steps. For example, to refer to the property environment.name, use the following code:

    ```
    $properties.get("environment.name")
    ```

    Similarly, if the step `myStep` creates the output property `outputProperty1`, you can refer to the property in the notification template with the following code:

    ```
    $properties.get("myStep/outputProperty1")
    ```

    You use the same syntax to refer to other properties, too. For example, if an application has an application property that is named `myApplicationProp`, you can refer to that property with the following code:

    ```
    $properties.get("application/myApplicationProp")
    ```

    Similarly, you can refer to environment properties with code that is similar to the following example:

    ```
    $properties.get("environment/myEnvironmentProp")
    ```

5.  Restart the server.The server loads notification templates at start time, so when you change a template, you must restart the server before you can use it.

Now you can use this template as part of a notification scheme. See [Creating Notifications in a Notification Scheme](../../com.udeploy.doc/topics/notify_create.md).

