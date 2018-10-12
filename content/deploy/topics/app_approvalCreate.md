# Approval process {#app_approvalcreate .concept}

An approval process specifies the job that needs approval and the role of the approver.

You must create an approval process if the **Require Approvals** check box is selected for an environment. If a scheduled deployment that requires approval reaches its start time and the approval is not given, the process does not run and acts as a rejected request. To resubmit a request, you must request a new process. If a process with an approval does not have a scheduled deployment time, the process remains idle until a response is made.

**Tip:** The environment developer can also select the **No Self-Approvals** check box that follows the **Require Approvals** check box. When this check box is selected, the user who sets up of the approval process cannot subsequently approve the process.

To create an approval process, display the Approval Process Design pane \(**Applications** \> **application name** \> **Environments** \> **Environment: environment name** \> **Approval Process**.

After the pane is displayed, select the steps that need approval from the process editor. The steps are based on job type and the role of the approver. You have the option of selecting three job types: the application, component, or environment. For help on the process editor, see [Processes](comp_workflow.md).

To view the status of the request, display the Deployment Detail pane on the Reports tab. If a request is approved, it is displayed as a success. However, if the request was rejected, it shows as failed. If a request is failed, display the Application Process Request by clicking **view request**.

If a comment is made regarding the process, you can view it by clicking the log push button in the actions column on the Application Process Request.

-   **[Work items](../topics/app_approvals_workitems.md)**  
If a job requires approval, an approval process must be created. Then, the job displays in the approver’s Work Items tab.

**Parent topic:** [Applications](../topics/applications_ch.md)

