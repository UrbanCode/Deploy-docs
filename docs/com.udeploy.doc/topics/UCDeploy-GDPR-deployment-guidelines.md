# UrbanCode Deploy, HCL UrbanCode Deploy with Patterns Considerations for GDPR Readiness



___________________________________________________________________________________________________
### For PID(s): 5725-M54, 5725-R35
## Notice:

This document is intended to help you in your preparations for GDPR readiness. It provides information about features of UrbanCode Deploy, HCL UrbanCode Deploy with Patterns that you can configure, and aspects of the product's use, that you should consider to help your organization with GDPR readiness. This information is not an exhaustive list, due to the many ways that clients can choose and configure features, and the large variety of ways that the product can be used in itself and with third-party applications and systems.

__Clients are responsible for ensuring their own compliance with various laws and regulations, including the European Union General Data Protection Regulation. Clients are solely responsible for obtaining advice of competent legal counsel as to
the identification and interpretation of any relevant laws and regulations that may affect the clients' business and any actions the clients may need to take to comply with such laws and regulations.__

__The products, services, and other capabilities
described herein are not suitable for all client situations and may have restricted
availability. HCL does not provide legal, accounting, or auditing advice or represent or
warrant that its services or products will ensure that clients are in compliance with
any law or regulation.__



___________________________________________________________________________________________________


### Table of Contents
1. GDPR
2. Product Configuration for GDPR
3. Data Life Cycle
4. Data Collection
5. Data Storage
6. Data Access
7. Data Processing
8. Data Deletion
9. Data Monitoring
10. Responding to Data Subject Rights


___________________________________________________________________________________________________
### GDPR

General Data Protection Regulation (GDPR) has been adopted by the European Union ("EU") and applies from May 25, 2018.

#### Why is GDPR important?

GDPR establishes a stronger data protection regulatory framework for processing of personal data of individuals. GDPR brings:

* New and enhanced rights for individuals
* Widened definition of personal data
* New obligations for processors
* Potential for significant financial penalties for non-compliance
* Compulsory data breach notification


#### Read more about GDPR
* (EU GDPR Information Portal)[https://www.eugdpr.org/]
* (HCL.com/GDPR website)[https://HCL.com/GDPR]


___________________________________________________________________________________________________
### Product Configuration - Considerations for GDPR Readiness


The following sections provide considerations for configuring UrbanCode Deploy, HCL UrbanCode Deploy with Patterns to help your organization with GDPR readiness.


___________________________________________________________________________________________________
### Data Life Cycle

#### What is the end-to-end process through which personal data go through when using our offering?
HCL UrbanCode Deploy (UCD) uses a client-server model with a network of agents and relays that communicate with target systems. The server provides the web-based front-end and core services, such as workflow, agent management, and security. Services can be consumed by clients and agents or other services. Deployments are orchestrated by the server and performed by agents distributed throughout the network. Clients access the server through web browsers, the REST API, or the command-line client.

Server-agent communication is done with Java Message Service (JMS) and HTTPS protocols. JMS is used for basic commands and information
that is exchanged between the server and an agent. HTTPS is used for file transfers between the server and agents, such as uploading or downloading component version artifacts.

The core installation of UCD includes a server, agents, and a license server. Agents, which do the application processing,  can be installed on cloud environments, virtual machines (VMs), containers, or physical systems. The artifact repository comes with a client application that provides remote access to the repository. In addition to the client application, the artifact repository exposes REST-based web services.

There are several third-party products that interact with UCD via plug-ins, and might exchange data. Some of these are HCL-owned, and many others are provided by other technology suppliers. 

#### What types of data flow through UCD?

As a software deployment an integration engine, UCD does not require sensitive personal data to be gathered from the client or the client's clients.




##### Personal data used for online contact with HCL


UrbanCode Deploy, HCL UrbanCode Deploy with Patterns clients can submit online comments/feedback/requests to contact HCL about product topics in a variety of ways.

Typically, only the client name and email address are used, to enable personal replies for the subject of the contact, and the use of personal data conforms.


___________________________________________________________________________________________________
### Data Storage

Deployments are orchestrated by the server and performed by agents distributed throughout the network. The file store, CodeStation, contains log files, artifacts, and other non-structured data objects. Reporting tools can
connect directly to the relational database.

The file store manages artifacts in a secure and and tamper-proof repository that ensures deployed artifacts are identical to
those tested in preproduction environments.




#### Protection
UCD uses several technologies to provide security. Some features cannot be disabled, such as Transport Layer Security (TLS) for
JMS communication. Other features can be configured to meet client requirements. Some features are enabled by default, such as end-to-end JMS encryption,
while others are disabled by default, such as mutual authentication.



___________________________________________________________________________________________________
### Data Access

* The UCD team- and role-based security system manages user interactions and secures product features.
Roles control virtually every product area, including the objects that users can create and who can
modify the security system itself. User-created objects are managed by teams. Team members can only access objects, such as applications,
managed by their team. Team members interact with team-managed objects according to the permissions granted to their role.

Read more:
	* [UCD team-based security model.](https://urbancode.hcldoc.com/deploy/712/com.udeploy.admin.doc/topics/security_ch.html)

#### Authentication:
UCD uses mutual authentication for JMS-based server-agent communication. In this mode, the server provides a digital certificate to each agent and agent relay, and each agent and agent relay provides one to the server. Certificate checks are performed by the JVM according to its own algorithm. Certificates can be issued from a certification authority (CA) if desired, in which instance certificates do not have to be swapped. The integrity of the content is established by the mechanisms built into TLS technology.

#### Logging administration activity:
Administrative activity is kept in the system logs. instances when the admin user adds a user or changes a users role and permissions are tracked in the log.


Please review:

https://urbancode.hcldoc.com/deploy/712/com.HCL.udeploy.doc/ucd_version_welcome.html


___________________________________________________________________________________________________
### Data Processing

Users control the way in which UCD interacts with data passing through it by their definition of application processes. A process is commonly constructed by a user acting in the role of “developer” working with the component plug-in toolkit. A process is composed of discrete building blocks (known as steps) that are joined together by the developer.

Agents play a central role in UCD processing. An agent is a lightweight process that runs on a deployment-target host and communicates with the UCD server. Agents perform the actual work of software deployment which relieves the server of the task. All processes requested by the server are executed on hardware assigned to agents.


#### Who has access to the Data?
Most customers import users from external LDAP realms. Clients filter LDAP account data for the information they need, such as user IDs, email addresses, and passwords. Groups that the imported users belong to are also
imported.

Permissions are assigned to roles and users and groups are placed into roles when they are placed onto teams. Users without roles have read-only privileges and cannot access data let alone modify it.

#### Encryption:

Communication between server and agents uses a JMS-based (Java Message Service) protocol and can be
secured using SSL and TLS, with optional mutual key-based authentication for each end-point. This communication
protocol is stateless and resilient to network outages. End-to-end JMS encryption ensures that agents cannot send messages to one another after they are connected to the JMS mesh. It also ensures that JMS clients cannot read messages that are not sent to them. End-to-end encryption ensures that agents do not accept messages from rogue servers or other malicious entities.

When mutual authentication mode is active, UCD uses it for JMS-based server-agent communication. In this mode, the server provides
a digital certificate to each agent and agent relay, and each agent and agent relay provides one to the server. Certificate checks are performed by the
JVM according to its own algorithm. Certificates can be issued from a certification authority (CA) if desired. The integrity of the content is established by the mechanisms built into TLS technology.

Unless the client uses a certification authority, the server stores the certificate from each agent in its trust store, and each agent stores the server’s certificate in its trust store. If the client uses agent relays, certificates are swapped between agents, agent relays, and the server. Connections are rejected if the recipient cannot find the sender’s certificate in its trust store.


Please review:

  https://urbancode.hcldoc.com/deploy/712/com.HCL.udeploy.doc/ucd_version_welcome.html


___________________________________________________________________________________________________
### Data Deletion

When client-created objects are deleted, they are removed from the UCD user interface. For auditing purposes, deleted objects remain in the database. 

Please review:

https://urbancode.hcldoc.com/deploy/712/com.HCL.udeploy.doc/ucd_version_welcome.html


___________________________________________________________________________________________________
### Data Monitoring

With an external monitoring tools, clients can use Managed Beans (MBeans) to review numerous details about UCD, such as statistics that specify how many components are available or see how long it takes for an application process to run to completion. Clients can use these statistics and details to assess the health of their deployments and deployment processes.

#### Activity monitoring
Audit and diagnostic logs are under user control. Clients control the amount of user activity maintained and the frequency with which it is stored.

Please review:

https://urbancode.hcldoc.com/deploy/712/com.HCL.udeploy.doc/ucd_version_welcome.html


___________________________________________________________________________________________________
### Responding to Data Subject Rights

On premises product managed by the client, please review links provided in earlier sections for configuration information.




___________________________________________________________________________________________________
