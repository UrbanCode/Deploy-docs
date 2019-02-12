# Introduction

In this tutorial, you deploy a simple web application to a new environment with HCL® UrbanCode™ Deploy. You create a snapshot of the components in an application, and then deploy the snapshot to an environment.

You can use HCL UrbanCode Deploy to facilitate a continuous deployment pipeline in your release cycle. You can plan and automate the deployment of complex applications to development, test, and production environments. You can use this tool to deploy applications as often as needed and to as many different environments as you require. By using snapshots, you combine the planning and automation capabilities of HCL UrbanCode Deploy with the ability to quickly and precisely control the contents of your delivery pipeline's environments.

When you develop a complex application, you use many tests to validate that all the application components work together. After your application passes the tests, you must ensure that you promote the correct collection of application components to the next step in your continuous delivery pipeline. However, you must ensure that you promote the set of components that passed the tests. In HCL UrbanCode Deploy, you use snapshots. A snapshot specifies all the versions of an application’s components that are used in an environment. The snapshot also specifies versions of configuration, such as deployment processes, that are used to deploy those components. If you use snapshots to deploy to different environments in your continuous delivery pipeline, you no longer must track and promote individual components through the environments in your pipeline. Instead, you promote configurations of components that were tested together. This ability to promote tested snapshots of components to environments is essential in maintaining a continuous delivery pipeline.

In this tutorial, you use snapshots to deploy the components, application, and processes that you created for a three-tiered web application to a new environment. In most cases, you use snapshots to manage complex deployment environments in HCL UrbanCode Deploy. You typically use snapshots to control deployments to different environments on different servers. However, for simplicity, in this lesson you use snapshots to deploy an application to two different environments on a single server.

## Learning objectives

In this tutorial, you learn how to complete these tasks:

-   Create a snapshot of an environment's components to quickly deploy its application to another environment.
-   Configure environments on which to deploy applications.
-   Select a snapshot while you run an application process to promote the snapshots to a new environment.

## Time required

This tutorial takes approximately 1 hour to finish. If you explore other concepts that are related to this tutorial, it might take longer to complete.

## System requirements

To run this tutorial, you must have an installation of HCL UrbanCode Deploy, version 6.0 or later

## Prerequisites

-   Make sure that you completed the [Deploying a simple web application](webapp_abstract.md) tutorial and have access to its HCL UrbanCode Deploy server and computers, virtual images, or cloud instances.
-   You must have an account on the server with the permissions to create and edit environments and to run processes.
-   You must know the user names and passwords for the MySQL database and Apache Tomcat manager role that you configured in the [Deploying a simple web application](webapp_abstract.md) tutorial.

**Parent topic:** [Creating and deploying snapshots](../../com.udeploy.tutorial.doc/topics/snapshot_abstract.md)

