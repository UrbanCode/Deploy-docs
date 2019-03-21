# Agents

An agent is a lightweight process that runs on a deployment-target host and communicates with the HCL® UrbanCode™ Deploy server.

There are two agent types. Web agents use WebSocket connections and HTTP\(S\) for agent-server communication. [Web agents were introduced with version 7.0.0](web_agents.md#). Agents delivered before version 7.0.0 are called JMS agents. JMS agent use JMS and HTTP\(S\) to communicate with the server. You determine agent type when you install the agent.

Agents do the actual work of deploying components and so relieve the server from the task, making large deployments that involve thousands of targets possible. Usually, an agent runs on the same host on which the resources it handles are located. A single agent can handle all the resources on its host. If a host has several resources, an agent process is started separately for each one. Depending on the number of hosts in an environment, a deployment might require many agents. For example, a test environment might contain a single web server, a single middleware server, and a single database server all running on the same host. A deployment to this environment might have one agent and three separate resources.

Agents have one or more matching agent resources, which represent the agents in the resource tree.

Agents are installed with the batch files that are provided with the installation files, see [Installing agents from the command line](../../com.udeploy.install.doc/topics/agentInstall.md). You can install agents on UNIX™ systems with the web application. Agents are run with the batch files that are included with the installation package.

Agents are unobtrusive and secure. Agent communications use SSL encryption and mutual key-based authentication for server-agent communication and employ JMS, HTTP, and HTTPS protocols to communicate with the server. See [Agent security and communication](arch_agents.md#).

Agent configuration consists of assigning an agent to at least one environment; agents can be assigned to multiple environments. If an agent is assigned to several environments, it can do work on behalf of all of them.

To manage agents, see [Agents and agent relay configuration](configure_agents.md).

## Agent prototypes

An agent prototype is a resource that represents one or more agents that are not yet installed or connected to an environment. You can use agent prototypes in resource templates to represent resources that are not yet available. When you import a resource template from the cloud, an agent prototype is created for each node in the cloud pattern.

If you create a resource template instead of importing a resource template from the cloud, you can specify an **Agent Name Pattern** for any agent prototype that you add to the resource template. The agent name pattern can include the properties `${p:application.name}` and `${p:environment.name}`, but no other properties or wildcards.

