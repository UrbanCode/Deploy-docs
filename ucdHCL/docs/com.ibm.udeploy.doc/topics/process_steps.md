# Process step types and logic

When you design processes, you use different kinds of process steps and joining techniques. You can assign properties to process steps and use them to control step execution.

-   **[Conditional processes](../topics/comp_process_conditional.md)**  
Every connection \(except connections from the Start step\) has a delete tool and conditional flag. The conditional flag sets a condition on a connection.
-   **[Switch steps](../topics/comp_process_switch.md)**  
A switch step is a utility step that you use to branch process, based on the value of a property.
-   **[Branching and joining steps](../topics/comp_process_join.md)**  
You can branch processes so that multiple steps run at the same time. You can also merge processes to return to running a single step at a time.
-   **[Process step properties](../topics/comp_process_step_properties.md)**  
All steps have the following properties: `exitCode`, `status`, and `lines of interest` \(LOI, which are items that the post-processing script finds in the step's output log\).
-   **[Process step preconditions](../topics/comp_process_step_precondition.md)**  
Most steps in a process can have a precondition. If the **Precondition** field is available, the process supports a precondition. This precondition determines whether the step runs. Like post-processing scripts, preconditions use JavaScript™ 1.7.
-   **[Post-processing scripts](../topics/comp_postProcess.md)**  
Post-processing scripts run after a step finishes. Typically, post-processing scripts ensure that expected results occurred.

**Parent topic:** [Processes](../topics/comp_workflow.md)

