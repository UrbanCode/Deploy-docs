# Building and deploying mobile applications {#buildinganddeployingmobileapplications .task}

You can set up your development environment so that you can build your mobile applications and, by using the IBM® MobileFirst Platform Foundation \(formerly Worklight®\) plug-in forIBM UrbanCode® Deploy, deploy the build results to the MobileFirst Platform Foundation Server.

Ensure that the following software is installed and running:

-   IBM UrbanCode Deploy
-   IBM MobileFirst Platform Foundation Server with the Application Center and Console running.
-   IBM MobileFirst Platform Foundation Studio

Extra software might be required, such as:

-   Source control management \(SCM\) system.
-   Build engine.
-   Application server.
-   Database.

Before you can build and deploy mobile applications to the MobileFirst Platform Foundation Server, you must complete the following configuration steps:

1.  [Configure the build system](plugins_worklight_buildresources.md).
2.  Configure IBM UrbanCode Deploy, including the following steps:
    -   Create components.
    -   Create component processes or application processes that include steps from the MobileFirst Platform Foundation plug-in to deploy the application. See [Deploying mobile applications](plugins_worklight_deploy.md).
3.  [Configure Worklight Server Console](plugins_worklight_configserver.md), including the following steps:
    -   Create and configure a database.
    -   Configure the MobileFirst Platform Foundation project web archive \(WAR\) file.

1.  After you set up the build, IBM UrbanCode Deploy and MobileFirst Platform Foundation Server console, you can build and deploy mobile applications by using the following high-level steps:
2.  Check in \(commit\) changes from MobileFirst Platform Foundation Studio into a source control management \(SCM\) system.
3.  Build the application and add a version to IBM UrbanCode Deploy. 

    **Tip:** Assign a version to the mobile application that is deployed to the Application Center. This version must match the version that is assigned in IBM UrbanCode Deploy.

    For example, if the mobile application has a commercial version of 1.0 on the Application Center and the internal version from the latest build is 16, assign version 1.0.16 to the application in IBM UrbanCode Deploy. Keeping the version numbers synchronized helps you to recover if you encounter a problem. For example, if the latest version of the mobile application was not deployed successfully to the Application Center.

4.  Request deployment in IBM UrbanCode Deploy. 
5.  View the mobile artifacts in the MobileFirst Platform Foundation Console, install, and test the application from the Application Center. 

The mobile application artifacts are deployed to the MobileFirst Platform Foundation Server and can be installed on the target device.

Optionally, create extra component and application processes in IBM UrbanCode Deploy to [roll back deployments](plugins_worklight_rollback.md) \(for example, to recover from an error condition or an incomplete deployment.\)

-   **[Building mobile applications](../topics/plugins_worklight_build.md)**  
To set up a continuous integration and delivery cycle for your mobile applications, you must build the mobile application artifacts before you deploy them to the IBM MobileFirst Platform Foundation Server. TheRational® solution for Collaborative Lifecycle Management, MobileFirst Platform Foundation, and IBM UrbanCode Deploy products integrate to help automate the build and deployment of mobile applications.
-   **[Adding mobile artifacts to IBM UrbanCode Deploy](../topics/plugins_worklight_add_artifacts.md)**  
You can use the build scripts to add your build artifacts to IBM UrbanCode Deploy for deployment to the IBM MobileFirst Platform Foundation Server.
-   **[Configuring the MobileFirst Platform Foundation Server](../topics/plugins_worklight_configserver.md)**  
You must configure the IBM MobileFirst Platform Foundation Server before you can run the process steps to deploy mobile application artifacts.
-   **[Deploying mobile applications](../topics/plugins_worklight_deploy.md)**  
You can use the process steps in the IBM MobileFirst Platform Foundation \(formerly Worklight\) plug-in to deploy mobile applications to MobileFirst Platform Foundation Server.
-   **[Rolling back mobile applications](../topics/plugins_worklight_rollback.md)**  
There are a number of ways to roll back a mobile application that is deployed to IBM MobileFirst Platform Foundation Server. One option is to remove the native application from the Application Center and then redeploy the application. Alternatively, you can manually roll back deployments.

**Parent topic:** [Applications](../topics/applications_ch.md)

