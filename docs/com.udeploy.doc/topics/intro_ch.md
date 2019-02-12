# Overview of HCL UrbanCode Deploy

Use HCL® UrbanCode™ Deploy to standardize and simplify the process of deploying software components to each environment in your development cycle.

HCL UrbanCode Deploy helps you meet the challenge of deploying software throughout your enterprise by providing tools that improve both deployment speed and reliability. The release automation tools in HCL UrbanCode Deploy provide complete visibility into n-tiered deployments. Use the tools to model processes that orchestrate complex deployments across every environment and approval gate.

By using plug-ins in HCL UrbanCode Deploy, you integrate the server with your existing middleware and organize code from your existing code repositories into components. You design processes to deploy your code by using steps that run each required task. Then, you organize your components into applications and create environments for each stage of your release process. Finally, you create an application process to set the deployment order of your components and deploy your application to an environment.

If you provision environments to selected clouds by using the blueprint designer, you can also use a full-stack approach to simultaneously model the application and infrastructure layers of your deployment in your blueprint designer. You can model the topology of your environment, specify which virtual images contain HCL UrbanCode Deploy components or Chef roles, and provision both the environment and components to your cloud in a single action.

-   **[Systems and topology overview](../topics/ov_systems.md)**  
HCL UrbanCode Deploy includes several systems, including a server and one or more agents. You can configure multiple topologies, including ones that use high availability, [containerized servers running in IBM Cloud Private](../com.udeploy.install.doc/topics/docker_cloud_over.dita), disaster recovery, and the blueprint designer, to meet your needs.
-   **[Elements overview](../topics/ov_elements.md)**  
The HCL UrbanCode Deploy elements that you use to model software deployments include applications, environments, and components.

**Parent topic:** [Overview](../topics/c_node_overview.md)

