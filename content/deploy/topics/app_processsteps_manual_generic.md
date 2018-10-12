# Manual Application Task \(Utility\) {#app_processsteps_manual .reference}

A manual task interrupts an application process until manual intervention is done. A task-interrupted process remains suspended until the targeted user or users respond. Typically, manual tasks are removed after the process is tested or automated.

**Tip:** 

Applications, components, and generic processes share some process steps. This step applies to application processes, component processes, and generic processes. This step applies to application processes that are associated with application templates. However, the generic process step includes the **Comment Prompt** field.

Similar to approvals, triggered tasks alert targeted users. Alerts are associated with environment- or application-defined user roles. Affected users can respond \(approve\) by using the Work Items pane \(see [Work items](app_approvals_workitems.md)\). Unlike approvals, manual tasks can be incorporated within an application process.

For information on using manual tasks in application processes, see [Creating manual application tasks](app_tasks_creating.md).

|Field|Description|
|-----|-----------|
|**Name**|The name for the manual task.|
|**Only Allow Deploying User To Complete**|Restrict approval to the user who started the deployment.|
|**Notification Template**|Specify a notification template. The individual tasks map to the notification scheme used by the application \(see [Creating Notifications](../../com.ibm.udeploy.admin.doc/topics/notify_create.md)\). If you do not want notifications created for the task, select **None**.|
|**Properties**|Optionally, add one or more properties to the task.|
|**Require Comment**|Select to require that users must add a comment about this manual task.|
|**Comment Prompt**|**Note:** This field applies only to generic process steps.

Enter the text that requests users to add a comment about this manual task.|

**Parent topic:** [Process steps: Reference](../topics/app_processSteps.md)

