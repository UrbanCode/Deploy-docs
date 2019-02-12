# Introduction

In this tutorial, you deploy a simple web application with HCL® UrbanCode™ Deploy. You create components, create an application that contains those components, and then deploy the components to an environment.

HCL UrbanCode Deploy helps you to plan and automate the deployment of complex applications to development, test, and production environments. It can deploy applications as often as needed, helping you to find problems early in the release cycle and provide predictability late in the release cycle.

The web application that you deploy in this tutorial is a simple three-tiered web application with a database, web interface, and application logic. You import these three components to the HCL UrbanCode Deploy server and create a single application that deploys these three parts. Then, you create automation instructions that are called processes that describe how to deploy each component. Finally, you use those processes to deploy the components automatically to a target system.

In later lessons, you update the components to a new version. Working with the sample application in this way demonstrates how you can manage a multipart application with HCL UrbanCode Deploy.

## Learning objectives

In this tutorial, you learn how to complete these tasks:

-   Import artifacts from a build to create a component in HCL UrbanCode Deploy.
-   Create component processes and application processes to automate deployment tasks.
-   Configure environments on which to deploy applications.
-   Run application processes to deploy the application components.
-   Update an application with new artifacts.

## Time required

This tutorial takes 2 - 3 hours to finish. If you explore other concepts that are related to this tutorial, it could take longer to complete.

## System requirements

To run this tutorial, you need the following resources:

-   An installation of HCL UrbanCode Deploy, version 6.2.2 or later
-   Two computers, virtual images, or cloud instances to use as agents for the HCL UrbanCode Deploy server

## Prerequisites

-   Make sure that you have access to an HCL UrbanCode Deploy server. For information about installing a server, see [Installing the server](../../com.udeploy.install.doc/topics/serverInstall.md).
-   The server must have the Apache Tomcat, IBM UrbanCode DBUpgrader, and FileUtils plug-ins installed. If you do not have access permissions to install plug-ins, ask the system administrator to install these plug-ins. For instructions, see [Installing plug-ins](../../com.udeploy.admin.doc/topics/settings_plugins.md). You can verify that the plug-ins are installed by clicking **Settings** \> **Automation Plugins** and finding Tomcat, DBUpgrader, and FileUtils in the list of installed plug-ins. The FileUtils plug-in is installed by default.
-   You must have an account on the server with the permissions to create and edit applications, environments, and components, and to create and run processes.

**Parent topic:** [Deploying a simple web application](../../com.udeploy.tutorial.doc/topics/webapp_abstract.md)

