# Application environments

An environment is a user-defined collection of resources that hosts an application.

An environment is the application's mechanism for bringing together components with the agent that deploys them. Environments are typically modeled on some stage of the software project lifecycle, such as development, QA, or production. A resource is a deployment target, such as a database or Java™ Platform, Enterprise Edition container. Usually, resources are found on the same host where the agent that manages them is located. A host can be a physical system, virtual machine, or be cloud-based.

Environments can have different topologies, for example: an environment can consist of a single server; be spread over several servers; or spread over clusters of servers. Environments are assigned to specific applications. Although multi-tenant systems can be the target of multiple applications, most IT organizations use application-specific environments. Additionally, approvals can be assigned to specific environments.

HCL® UrbanCode™ Deploy maintains an inventory of every artifact that is deployed to each environment and tracks the differences between them.

Environment properties can be created with the environment's Properties pane \(**Applications** \> **selected application** \> **Environments** \> **selected environment** \> **Properties**\).

A value that is set on a component environment property overrides an environment property that has the same name.

Referenced: `${p:environment/propertyName}`.

