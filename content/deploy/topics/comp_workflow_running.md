# Running processes {#comp_workflow_running .task}

The way you run a process is different for each type of process.

To run a process, you must have permissions to access the processes and to run processes on the target agent resource.

 Component processes
 :   You cannot run a component process directly. Instead, you add one or more component processes to an application process and then run the application process.

  Application processes
 :   To run an application process, you must have an application environment. Click **Applications**, click the application, and then next to the environment, click **Request Process** ![](../images/request_process_icon.gif). Then, specify the application process and the versions of the components to use. For more information, see [Running application processes](app_process_run.md).

  Generic processes
 :   To run a generic process, click **Processes**, and then click the generic process. On the **Dashboard** tab for the process, specify a resource \(in most cases, an agent\) in the **Resource** list, and then click **Submit**.

    **Tip:** You can set a default resource for generic processes:

    1.  Click the generic process to open it.
    2.  Open the **Configuration** tab.
    3.  Click **Basic Settings**.
    4.  In the **Default Resource** field, specify the default resource to run the process on. In most cases, specify an agent.
    5.  Click **Save**.

 Each time you request a process, the server keeps a log of information about the process and the individual logs from each step. To download these logs, open the process request and click **Download All Logs**.

**Parent topic:** [Processes](../topics/comp_workflow.md)

