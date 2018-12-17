# SSL configuration

With Secure Sockets Layer \(SSL\) technology, clients and servers can communicate securely by encrypting all communications. Data is encrypted before it is sent and decrypted by the recipient. This communication cannot be deciphered or modified by third-parties. In addition to encryption, SSL can also support authentication.

HCL® UrbanCode™ Deploy servers and agents communicate via HTTP and Java™ Message Service \(JMS\) protocols. JMS is used for basic commands and information that is exchanged between the server and an agent. Typically, HTTP is used for file transfers between the server and an agent. For example, HTTP is used when an agent is downloading a new plug-in, or when an agent is uploading or downloading version artifacts.

For JMS connections, HCL UrbanCode Deploy supports communication via SSL in two modes: unauthenticated and mutual authentication. In unauthenticated mode, communication is encrypted but users do not have to authenticate or verify their credentials. SSL unauthenticated mode can also be used for HTTP communication. You can implement this mode for HTTP communication during server, agent, or agent relay installation. You can also activate it afterward.

**Important:** 

HCL UrbanCode Deploy automatically uses SSL in unauthenticated mode for JMS-based communications between the server and agents. You cannot disable SSL in unauthenticated mode, but you can enable mutual authentication for JMS-based server-agent communication. Because agent relays do not automatically activate SSL security, you must turn on SSL security when you install an agent relay or at least before you connect to the relay. Without SSL security active, agent relays cannot communicate with the server or remote agents.

In mutual authentication mode, servers, local agents, and agent relays each provide a digital certificate to one another. A digital certificate is a cryptographically signed document that is intended to assure others about the identity of the certificate's owner. HCL UrbanCode Deploy certificates are self-signed. When mutual authentication mode is active, HCL UrbanCode Deploy uses it for HTTP-based server, local agents, and agent relay communication.

In mutual authentication mode, the HCL UrbanCode Deploy server provides a digital certificate to each local agent and agent relay, and each local agent and agent relay provides one to the server. Agent relays, in addition to swapping certificates with the server, must swap certificates with the remote agents that use the relay. Remote agents do not have to swap certificates with the server, just with the agent relay it uses to communicate with the server. This mode can be implemented during installation or activated afterward.

**Note:** When you use mutual authentication mode, you must turn it on for the server, agents, and agent relays; otherwise, they cannot connect to one another. If one party uses mutual authentication mode, they all must use it.

-   **[Configuring mutual authentication](../../com.ibm.udeploy.install.doc/topics/ssl_mutual_auth.md)**  
To use mutual authentication, servers and JMS agents must exchange keys. You export a server key as a certificate and import it into the JMS agent keystore. Then, you reverse the process by exporting the agent key and importing it into the server keystore.
-   **[Enabling server identity verification](../../com.ibm.udeploy.install.doc/topics/ssl_addl_security.md)**  
Starting with version 6.2.1.1 of the product, you can enable extra security to configure the agents to verify the identity of the server for communication that uses the HTTPS protocol.
-   **[Ensuring end-to-end JMS encryption](../../com.ibm.udeploy.install.doc/topics/ssl_addl_security_2.md)**  
All JMS traffic between the JMS agent and the server is encrypted with Transport Layer Security \(TLS\). However, starting with version 6.2.2 of the HCL UrbanCode Deploy, the server creates by default a unique key for JMS agents that connect to it and encrypts all JMS traffic to the agent with this key. This encryption ensures that instructions that are meant for an agent can't be read or used by another client on the JMS mesh.
-   **[Supported TLS and SSL protocols and ciphers](../../com.ibm.udeploy.install.doc/topics/ssl_compatibility.md)**  
HCL UrbanCode Deploy supports multiple SSL protocols and ciphers for communication between servers.
-   **[Sharing secured properties among servers](../../com.ibm.udeploy.install.doc/topics/ssl_mutual_authServers.md)**  
To share applications that have secured properties among HCL UrbanCode Deploy servers, exchange keys from each server's encryption keystore.
-   **[Configuring SSL on Apache Tomcat and LDAP servers](../../com.ibm.udeploy.doc/topics/ssl_config.md)**  
The steps for configuring secure HTTP connections with the HCL UrbanCode Deploy server are similar to the steps for any Java Platform, Enterprise Edition server.
-   **[Implementing custom trust stores](../../com.ibm.udeploy.admin.doc/topics/ssl_truststores.md)**  
A trust store defines the roots of the certificate trust chain. Typically, these are the certificate authority root certificates that sign other certificates. It can also be end entity certificates that are directly trusted. Java® includes a default trust store that contains certificate authority root certificates for many well-known authorities. This trust store is a file called cacerts and is contained in the Java installation. The file has the same format as a keystore, but it never contains a private key. It is possible to modify or replace this file to alter the trust roots with the keytool program. Otherwise, a custom trust store must be used instead.

**Parent topic:** [Managing security](../../com.ibm.udeploy.admin.doc/topics/security_ch.md)

**Parent topic:** [Configuring](../topics/c_node_configuring.md)

