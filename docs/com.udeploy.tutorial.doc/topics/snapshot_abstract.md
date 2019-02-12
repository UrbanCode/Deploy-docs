# Creating and deploying snapshots

In this tutorial, you deploy a simple web application to a new environment with HCL® UrbanCode™ Deploy. You create a snapshot of the components in an application, and then deploy the snapshot to an environment.

## Learning objectives

In this tutorial, you learn how to complete these tasks:

-   Create a snapshot of an environment's components to quickly deploy its application to another environment.
-   Configure environments on which to deploy applications.
-   Select a snapshot while you run an application process to promote the snapshots to a new environment.

## Time required

Approximately 1 hour

**Note:** You must complete [Deploying a simple web application](webapp_abstract.md) before you begin this tutorial.

-   **[Introduction](../../com.udeploy.tutorial.doc/topics/snapshot_intro.md)**  
In this tutorial, you deploy a simple web application to a new environment with HCL UrbanCode Deploy. You create a snapshot of the components in an application, and then deploy the snapshot to an environment.
-   **[Configuring the server and target system](../../com.udeploy.tutorial.doc/topics/snapshot_configure_agent.md)**  
Modify the HCL UrbanCode Deploy server that you used in the previous tutorial. Create another agent resource and incorporate a new environment property to allow for easy reuse.
-   **[Lesson 1: Adding snapshots](../../com.udeploy.tutorial.doc/topics/snapshot_snapshots.md)**  
Creating a snapshot involves saving a collection of component versions that are part of an application.
-   **[Lesson 2: Creating an environment](../../com.udeploy.tutorial.doc/topics/snapshot_environment.md)**  
Environments are deployment targets for the application components that you specify. You create another environment in the application's delivery pipeline to facilitate multiple active applications. You apply an agent resource and specify which components the agent resource deploys.
-   **[Lesson 3: Deploying the snapshots](../../com.udeploy.tutorial.doc/topics/snapshot_deploy.md)**  
To promote the snapshot to an environment, apply the snapshot when you run the application process.
-   **[Summary](../../com.udeploy.tutorial.doc/topics/snapshot_summary.md)**  
In this tutorial, you created and deployed a snapshot to an environment in HCL UrbanCode Deploy.

**Parent topic:** [Tutorials](../../com.udeploy.doc/topics/c_node_tutorials.md)

