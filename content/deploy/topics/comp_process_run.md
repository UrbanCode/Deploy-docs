# Running component processes {#comp_process_run .task}

Component processes are typically run from within application processes. However, you can also run component processes directly to test the processes or to correct an error in an urgent situation.

To run a component process in an application process, add the appropriate step to the application process and specify the component process. For example, to run a deployment component process, use the Install Component step. The step that you use depends on the type of component process. For more information, see [Component process types](comp_process_types.md).

You can run certain types of component process from generic processes. See [Generic processes](genProcess_ch.md).

You can also run component processes directly:

1.  Click an application, and go to the **Components** tab.
2.  Next to the component, click **Run Process**.
3.  In the **Environment** and **Resource** lists, select where to run the process.
4.  In the **Process** list, select the component process.
5.  If the component process requires a component version, in the **Version** list, select the component version.
6.  If the component process requires other properties, specify values for those properties.
7.  Click **Submit**.

**Parent topic:** [Component processes](../topics/intro_component_processes.md)

