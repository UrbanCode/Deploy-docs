# Creating manual application tasks {#app_tasks_creating .task}

A manual application task interrupts an application process until manual intervention is done. To create a manual task, add a manual step to an application process and select a notification template.

1.  Open an application process in the process editor. 
2.  From the **Utility Steps** folder, add a **Manual Application Task** step to the process. 
3.  In the Edit Properties window, specify the following properties for the step:

     Name
     :   Specify a name for the step.

      **Notification Template**
     :   Specify the notification template to use. These templates refer to the notification scheme that is used by the application \(see [Creating Notifications](../../com.ibm.udeploy.admin.doc/topics/notify_create.md)\). If you select **None**, notifications are not created when the step runs.

      Only Allow Deploying User To Complete
     :   Restrict approval to the user who started the deployment.

      Properties
     :   Optionally, add one or more properties to the task. You can use these properties later in the process just like output properties from other steps.

      **Who can approve this task**
     :    **Any User**
 :   Any user can approve the task.

  **Role Member By Environment**
 :   Specify an environment role that can approve the task.

  **Role Member By Application**
 :   Specify an application role that can approve the task.

  4.  Click **Save** to save the properties for the step.
5.  Include the manual task in the process as with any other step.
6.  Save the process.

When you run the process, it pauses at this step, sends a notification, and waits for approval before the process continues. To approve the task and resume the process, click the **Respond** link for the step in the process log, click **Approve**, and then click **Submit**. You can also resume the process from the Work Items tab.

**Parent topic:** [Applications](../topics/applications_ch.md)

