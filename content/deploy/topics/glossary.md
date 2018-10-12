# Glossary {#glossary .reference}

This glossary provides terms and definitions for theIBM® UrbanCode® Deploy software and products.

The following cross-references are used in this glossary:

-   *See* refers you from a nonpreferred term to the preferred term or from an abbreviation to the spelled-out form.
-   *See also* refers you to a related or contrasting term.

For other terms and definitions, see the [IBM Terminology website](http://www-306.ibm.com/software/globalization/terminology/) \(opens in new window\).

 [A](#) [B](#) [C](#) [D](#) [E](#) [F](#) [G](#) [I](#) [L](#) [P](#) [R](#) [S](#) [T](#) [U](#) [V](#) 

## A {#gloss_A}

 agent
 :   A program that runs on a remote computer and communicates with the IBM UrbanCode Deploy server. Agents run processes on deployment target systems.

  agent relay
 :   A communication proxy for agents that are located behind a firewall or in another network location.

  application
 :   One or more computer programs or software components that provide a function in direct support of a specific business process or processes.

  application environment
 :   A user-defined collection of resources that hosts an application. These application environments refer to environments that are created to be environments in IBM UrbanCode™ Deploy.

  application process
 :   A process that is associated with an application. Unlike a component or generic process, an application process is created from application-level steps. Typically, an application process invokes component processes, and orchestrates multi-component deployments. See also [component process](#x7204618), [generic process](#x7205165), [process](#x2003927).

  artifact
 :   A deployable item such as a file, image, database, configuration material, or anything else that is associated with a software project. By default, artifacts are stored in CodeStation repository.

  authentication realm
 :   An authentication realm manages users and determines user identity. It retrieves information from sources such as LDAP servers and Keystone identity services.

 ## B {#gloss_B}

 blackout
 :   A setting that prevents deployments and snapshots from being scheduled. Blackouts solely affect the environment and application that they are applied to.

  blueprint
 :   A Heat Orchestration Template \(HOT\) that specifies information about an automatic deployment of cloud resources to a virtual environment. Blueprints contain three sections: parameters, resources, and outputs.

  blueprint design server
 :   A server that hosts the blueprint designer and controls access to blueprints. It also hosts the cloud discovery service, which provides information about the available cloud resources to the blueprint designer. \(In previous versions, this system was the IBM UrbanCode Deploy with Patterns design server.\)

  blueprint designer
 :   The graphical user interface that models blueprints, which specify information about the automatic deployment of deployment of cloud resources to a virtual environment. Blueprints contain three sections: parameters, resources, and outputs.

 ## C {#gloss_C}

 cloud discovery service
 :   The component that provides information about available cloud resources, such as images and security groups, to the blueprint designer. \(In previous versions, this service was a component of IBM UrbanCode Deploy with Patterns.\)

  cloud project
 :   A functional ID with access to a cloud system. By accessing this cloud project, users can work with this functional ID to request cloud services that might not be available to their personal ID.

  CodeStation
 :   The artifact repository for IBM UrbanCode Deploy. CodeStation tracks artifact versions as they change and maintains an archive for each artifact.

  component
 :   A representation of deployable items and the user-defined processes that operate on them, usually by deploying them.

  component inventory
 :   A list of all of the resources on which a component is deployed. See also [environment inventory](#x7205077), [resource inventory](#x7205684).

  component process
 :   A series of user-defined steps that operate on component artifacts. See also [application process](#x2000181), [generic process](#x7205165), [process](#x2003927).

  component version
 :   See [version](#x2005676).

 ## D {#gloss_D}

 deployment
 :   A process that retrieves the output of a build, packages the output with configuration properties, and installs the package in a pre-defined location so that it can be tested or run.

 ## E {#gloss_E}

 engine
 :   A customized OpenStack Heat orchestration engine that interprets blueprints. Engines use blueprints as patterns for virtual environments.

  environment
 :   A user-defined collection of resources that hosts an application.

  environment inventory
 :   A list of all of the component versions that are deployed to an environment. See also [component inventory](#x7204610).

 ## F {#gloss_F}

 full version
 :   A component version that contains all of the artifacts in the component, as opposed to an incremental version. See also [incremental version](#x7260280), [version](#x2005676).

 ## G {#gloss_G}

 generic process
 :   Processes that are designed to run outside typical component or application processing. See also [application process](#x2000181), [component process](#x7204618), [process](#x2003927).

 ## I {#gloss_I}

 incremental version
 :   A component version that contains only the artifacts that are different from the previous version, as opposed to a full version. See also [full version](#x7260270), [version](#x2005676).

 ## L {#gloss_L}

 lifecycle model
 :   A template for managing dependencies, artifacts, and deployments associated with every build of a given project. Lifecycle models can be reused for separate projects.

  lock
 :   A means of preventing uncommitted changes made by one application process from being perceived by another application process and for preventing one application process from updating data that is being accessed by another process. A lock ensures the integrity of data by preventing concurrent users from accessing inconsistent data.

 ## P {#gloss_P}

 process
 :   Automated tasks that run on agents. See generic processes, component processes, and application processes. See also [application process](#x2000181), [component process](#x7204618), [generic process](#x7205165).

  property
 :   A variable that specifies a value that is provided during process deployment and is associated with a specific UrbanCode Deploy object. An individual property's value can be accessed only by certain types of related objects, such as environments, processes, and components.

 ## R {#gloss_R}

 relay servers
 :   A proxy that can be used to access agents behind a firewall. Relay servers enable network-to-network communication.

  resource
 :   A user-defined construct that is based on the architectural model of IBM UrbanCode Deploy. A resource represents a deployment target.

  resource inventory
 :   A list of all of the components that are deployed to an agent resource. See also [component inventory](#x7204610).

  role
 :   A job function that identifies the tasks that a user can perform and the resources to which a user has access. A user can be assigned one or more roles.

 ## S {#gloss_S}

 snapshot
 :   A collection of specific versions of components. Typically, a snapshot represents a set of component versions that are known to work together.

 ## T {#gloss_T}

 team
 :   A categorization that associates users with roles. When you assign a user to a team, you also assign that user to a role because roles are assigned to teams.

 ## U {#gloss_U}

 user
 :   A representation of an account on the server. Users can be members of groups. Rather than having its own list of users, the server imports accounts from authentication realms, including OpenStack Keystone services and LDAP servers.

 ## V {#gloss_V}

 version
 :   A group of resources that represent a particular version of a component. See also [full version](#x7260270), [incremental version](#x7260280).

  virtual image
 :   A stand-alone virtual environment, including operating system and binary files, that is used to define a virtual system.

  virtual machine
 :   A software implementation of a machine that executes programs like a real machine.

 