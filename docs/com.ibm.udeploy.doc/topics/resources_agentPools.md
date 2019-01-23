# Creating and managing agent pools

Similar to resource groups, agent pools help you organize and manage agents that are installed in different environments.

You can use an agent pool to spread the deployment processing work among participating agents and provide relief to otherwise overburdened agents. Users assign agents to pools and pools are assigned to resources, just like lone agents. When an agent pool is assigned to a resource, work items are sent to eligible agents. If you don't use a pool, then the agent that is assigned to the resource is assigned all the processing work regardless of its current workload. Such a workload might lead to bottlenecks.

**Tip:** The agent that does the actual work is chosen randomly from available online agents in the pool. The current workload that is running on the agents in the pool is not considered. The agent that was most recently selected to do work is not exempt from subsequent selections. The selected agent is always randomly selected from available online agents in the pool.

**Parent topic:** [Agents and agent relay configuration](../topics/configure_agents.md)

## Creating an agent pool

1.  To create an agent pool, specify the agents that are the members of the pool.
2.   From the **Resources** tab, click **Agent Pools.** 
3.   From the Agent Pools pane, click **Create Agent Pool**. The Create Agent Pool window opens.
4.   Specify the pool name. 
5.   Enter a description in the **Description** field. 
6.   To manage the teams that can access the agent pool, click the plus icon by **Teams**. 
7.   To add agents to the pool, click the **Add Agents** field. A list of the available agents appears.
8.   Select the agent or agents to add to the pool. You can filter the listed agents by entering search text into the field.
9.   When you are finished, click **Save**. 

## Managing agent pools

1.  You can manage agent pools from the web interface.
2.   To display the Agent Pools pane, click **Resources** \> **Agent Pools**. 
3.   Click an action link for the pool. Actions are described in the following table.

    |Action|Description|
    |------|-----------|
    |Edit|With this option, you can add or remove agents and edit the pool's name and description.|
    |Copy|Creates a pool with the same agents as the selected pool.|
    |Delete|Removes the agent pool.|

    To deploy a resource to an agent pool, the resource must be a child of the agent pool.


