# Running application processes

To run an application process, specify the environment to use and the process to run. In many cases, you also specify the component versions to deploy.

-   Create an environment.
-   Create an application process.

1.  Click **Applications**, click the application, and then next to the environment, click **Request Process** ![](../images/request_process_icon.gif). 
2.  In the **Run Process** window, in the **Process** list, select the application process.
3.  To skip component versions that have not changed since the previous deployment, select the **Only Changed Versions** check box.If you clear this check box, all of the component versions that you select are deployed, even if they are already in the inventory.
4.  If the process you selected deploys component versions, you must specify the component versions to deploy. In this case, you can use the component versions in a snapshot, or you can select component versions manually.
5.  To use the component versions in a snapshot, select the snapshot in the **Snapshot** list.
6.  To specify component versions manually, follow these steps: 
    1.  Click **Choose Versions**. 
    2.   In the Component Versions window, specify the component versions to use completing one of these actions: 

        -   To specify the versions for each component individually, click the **Add** link next to a component in the table, click **Version Lookups**, and then click one of these options:
            -   Click **Latest Available** to select the most recent component version at the time that you make this selection regardless of when the process runs. If you schedule a process to run, for example, a week after you make this selection and you want to use the most recent version that is available then, click **Latest Available at Execution Time**.
            -   Click **Latest with Status** to select the most recent component version at the time that you make this selection. If you schedule a process to run, for example, a week after you make this selection and you want to use the most recent version that has the specified status that is available at the later time, click **Latest with Status at Execution Time**.
            -   Click **Latest Available at Execution Time** to select the latest component version that is available when the process starts. The version that is used might be generated after you make this selection.
            -   Click **Latest with Status at Execution Time** to select components that have a status that you specify in the next dialog box. The version that is used might be generated after you make this selection.
            -   Click **Current Environment Inventory at Execution Time** to use the environment inventory that is available when the process starts. The environment inventory might be different from the inventory that is available when you make this selection.
        -   To specify versions for all the components at one time, click **Select For All**, and then click one of the following options:
            -   Click **Latest Available** to select the most recent component version at the time that you make this selection regardless of when the process runs. If you schedule a process to run, for example, a week after you make this selection and you want to use the most recent version that is available then, click **Latest Available at Execution Time**.
            -   Click **Latest with Status** to select the most recent component version at the time that you make this selection. If you schedule a process to run, for example, a week after you make this selection and you want to use the most recent version that has the specified status that is available at the later time, click **Latest with Status at Execution Time**.
            -   Click **Versions With Name** to select the most recent component version whose name matches a string.
            -   Click **Current Environment Inventory** to use the versions that are listed for that environment when you select it. This selection is typically related to the last version that was deployed to a certain environment of each component. For example, say that you deployed component A, version 1, to your environment. Then, in a separate deployment, you deployed an incremental version 1.1 to the same environment. If you look at the current environment inventory in the Application view, you see that the environment contains versions 1 and 1.1. Typically, you don't want to redeploy what is already there. However, this selection is useful when a deployment fails or is modified on the target computer itself, outside of HCL® UrbanCode™ Deploy. So if the deployment of version 1.1 succeeded on 10 agents but failed on two, you can schedule essentially a retry. Use of this selection is not common.
            -   Click **Latest Available at Execution Time** to select the latest component version that is available when the process starts. The version that is used might be generated after you make this selection.
            -   Click **Latest with Status at Execution Time** to select components that have a status that you specify in the next dialog box. The version might be generated after you make this selection.
            -   Click **Current Environment Inventory at Execution Time** to use the environment inventory that is available when the process starts. The environment inventory might be different from the inventory that is available when you make this selection.
            -   Click **None \(Clear All\)** to clear your selections.
        **Note:** If you select multiple versions for one component, the versions are installed in the order that you select them in the **Run Process** window.

    3.  Click **OK**.

        **Note:** Make sure to select a version for each component. If you do not select a version for a component, that component is not included in the application process.

7.  If the process has properties, specify values for those properties.
8.  To schedule the deployment for a later date, click **Schedule Deployment?** and then specify when to run the deployment.
9.  Click **Submit**.

The server runs the application process with the specified component versions. You can view the process requests by going to the **History** tab for the environment or application. Typically, resources are mapped for each component version that is deployed by the application process. You can use the same application process for different environments, some of which do not have mappings for all components. If you run an application process on an environment where not all components are mapped, the resulting status for those components is Not Mapped.

You can view the progress of the process by going to the **History** tab and opening the process request. The application process request shows each step in the process. Within each process, the steps are not shown in the order that they run in. Instead, steps are shown in the order of appearance in the process editor, from the steps at the top of the canvas to the steps at the bottom of the canvas.

**Parent topic:** [Application processes](../topics/app_process.md)

