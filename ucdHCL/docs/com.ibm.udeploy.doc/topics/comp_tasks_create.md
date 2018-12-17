# Creating component manual tasks

A component manual task interrupts a component process until manual intervention is done. To create a component manual task, add a manual step to a component process, and select a notification template.

A process that is interrupted by a manual task remains suspended until the targeted user or users respond. During new process testing, use manual tasks to test the results of steps. After testing, use manual tasks for tasks that are too complicated to automate. Remove manual tasks after testing or when processes are automated.

Similar to approvals, triggered tasks notify targeted users. Affected users can accept or reject the task by using the Work Items pane \(see [Work items](app_approvals_workitems.md)\). Unlike approvals, component manual tasks are incorporated within a component process. Do not use a component manual task in place of an approval process. To obtain approval for an entire component, create an approval process instead of a component manual task \(see [Creating an approval process](app_approvalCreate.md)\).

1.  Open a component process in the process editor.
2.  From the **Utility Steps** folder, add a **Manual Task** step to the process.
3.  In the Edit Properties window, specify the following properties for the step: 
    -   ****Name****

        Specify a name for the step.

    -   ****Notification Template****

        Specify a notification template. These templates map to the notification scheme that the application uses. \(See [Creating Notifications in a Notification Scheme](notify_create.md).\) If a scheme is not specified, the default scheme is used.

    -   **Properties**

        Optionally, add one or more properties to the task. You can use these properties later in the process just like output properties from other steps.

    -   ****Who can approve this task****

        -   ****Any User****

            Any user can approve the task.

        -   ****Role Member By Environment****

            Specify an environment role that can approve the task.

        -   ****Role Member By Application****

            Specify an application role that can approve the task.

4.  Click **Save** to save the properties for the step.
5.  Include the manual task in the process as with any other step.
6.  Save the process.

When you run the process, it pauses at this step, sends a notification, and waits for approval before the process continues. To approve the task and resume the process, click the **Respond** link for the step in the process log, click **Approve**, and then click **Submit**. You can also resume the process from the Work Items tab.

**Parent topic:** [Components](../topics/comp_ch.md)

