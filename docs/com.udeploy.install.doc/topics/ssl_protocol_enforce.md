# Enforcing the use of a security protocol or set of ciphers

For security reasons, ensure that all SSL connections to and from the UrbanCode Deploy server use the TLSv1.2 protocol, if the server uses a JVM that supports it. To configure SSL globally, follow these instructions [jdk.tls.disabledAlgorithms](https://www.ibm.com/support/knowledgecenter/en/SSYKE2_8.0.0/com.java.security.component.80.doc/security-component/jsse2Docs/disabledalgorithms.html).

The UrbanCode Deploy Server uses different communication protocols that rely on SSL at the transport level:

-   HTTPS for displaying the user interface
-   JMS for communication between server, relay and agents
-   LDAP to connect to LDAP and Active Directory servers
-   JDBC to connect to the database containing the schema of the UrbanCode Deploy server application

The material that follows explains how to enforce the usage of TLSv1.2.

**Environment**

Enforcing TLS 1.2 is possible if the UrbanCode Deploy server, relay, and agent are running a JVM version that supports this protocol. For more information on such JVM versions, see: [Oracle JRE and JDK Cryptographic Roadmap](https://www.java.com/en/jre-jdk-cryptoroadmap.html). For connections to external tools \(LDAP servers, Database servers, and middleware that the plug-ins deploy to\), consider that the connections fail if those external tools do not support TLSv1.2 after you enforce it as the only supported protocol in UrbanCode Deploy.

**UrbanCode Deploy Server: HTTPS protocol**

The HTTPS protocol is configured in this file: <server\>/opt/tomcat/conf/server.xml.

This file contains the following relevant entries:

```
  <Connector port="${install.server.web.https.port}"
               address="${install.server.web.ip}"
               server="SERVER"
               maxThreads="150"
               enableLookups="false"
               acceptCount="100"
               debug="0"
               connectionTimeout="20000"
               disableUploadTimeout="true"
               compression="1024"
               noCompressionUserAgents="gozilla, traviata"
               compressableMimeType="text/html,text/xml,text/javascript,text/css,text/plain,application/json"
               algorithm="${install.server.ssl.algorithm}"
               SSLEnabled="true"
               scheme="https"
               secure="true"
               clientAuth="false"
               URIEncoding="UTF-8"
               ciphers="${install.server.ssl.enabledCiphers}"
               sslEnabledProtocols="${install.server.ssl.enabledProtocols}"
               truststoreFile="conf/tomcat.keystore"
               truststoreType="jks"
               keystoreType="jks"
               keystoreFile="conf/tomcat.keystore"
               keystorePass="${tomcat.keystore.password}"
               keyAlias="server"
               />

```

To enforce TLSv1.2, add or modify the `server.ssl.enabledProtocols=TLSv1.2` property in this file:<server\>/conf/server/installed.properties. Note that this property might be missing, or it might be present and have a different value, including an empty value. The property is referred to as: $\{install.server.ssl.enabledProtocols\} in the server.xml file, but it is named: server.ssl.enabledProtocols in theinstalled.properties file.

**UrbanCode Deploy Server: JMS Protocol**

The JMS protocol is configured in this file: <server\>/conf/server/activemq.xml. The relevant entries are as follows:

```
<transportConnectors>
          <transportConnector uri="ah3://${server.host}:${server.jms.port}?transport.enabledProtocols=${install.server.ssl.enabledProtocols}&amp;transport.enabledCipherSuites=${install.server.ssl.enabledCiphers}"/>
        </transportConnectors>

```

This entry also refers to the $\{install.server.ssl.enabledProtocols\} protocol, which is named: server.ssl.enabledProtocols in the installed.properties. Therefore, when the installed.properties is updated, the configuration of JMS is also affected.

**UrbanCode Deploy Server: LDAP integration**

The UrbanCode Deploy server uses the LDAP client that is contained in the JRE that is running on the server. You must specify a URL for the LDAP server, which uses the `ldaps://` protocol that uses port 636 but dault to connect through SSL or TLS.

**Note:** The server.ssl.enabledProtocols file changes the SSLContext which might affect the LDAP connection that is opened.

**UrbanCode Deploy Server: JDBC connection to the database server**

JDBC is used to connect UrbanCode Deploy to the backend database.

**DB2**

See [configuring SSL support in a DB2 instance](https://www.ibm.com/support/knowledgecenter/en/SSEPGG_10.5.0/com.db2.luw.admin.sec.doc/doc/t0025241.html). Configure the DB2 instance according to the instructions, and test after you compete the configuration.

**Postgres**

Connection string: connectionString=jdbc:postgresql://dbhost/dummy?ssl=true jdbcDriver=org.postgresql.Driver jdbcJar=C:\\IBM\\UCD\\ucd6.2.3\\623agent1\\postgresql-42.1.4.jar.

Import the database certificate to the UrbanCode Deploy Agent Java keystore.

The latest available plug-in version is Version 11, [see](https://developer.ibm.com/urbancode/plugin/sql-jdbc-ibmucd/).

**Microsoft SQL Server**

1.  Your Microsoft SQL Server must support TLS v1.2. You must have the right FixLevel and KB 3052404 installed.
2.  Enable TLS v1.2.
    1.  Depending on the Microsoft SQL Server JDBC type 4 driver version you can pass in the JDBC a connection string that enforces the TLS 1.2 ;sslProtocol=TLSv1.2. protocol.
    2.  You can enforce TLS v1.2 on the JRE level that runs the UrbanCode Deploy server. Enabling TSLv1.2 has the following results:

        1.  Outgoing connections to the LDAP database all are made with TLS v1.2.
        2.  Incoming connections from UrbanCode Deploy agents, UrbanCode Deploy agent relays, and WebUI require TLS v1.2.
        These results can be undesirable if one of the involved components does not support TLS v1.2. You must make sure that the JDBC drivers support TLS v1.2. To ensure this support, change the jdk.tls.disabledAlgorithms line in jre/lib/security/java.security to jdk.tls.disabledAlgorithms=SSLv3, TLSv1, TLSv1.1. You can also pass the ucd-server/bin/set\_env JAVA\_OPTS string through a java.security file.

        **Note:** You cannot disable the SSLv2Hello, because it is used as the initial handshake from the UrbanCode Deploy agents with the UrbanCode Deploy server.

3.  For the JDBC connection string:

    See [understanding SSL Support](https://docs.microsoft.com/en-us/sql/connect/jdbc/understanding-ssl-support?view=sql-server-2017).

    The encrypt=true uses TLS/SSL.

    Do not blanket trustServerCertificate=false. Every SSL certificate from Microsoft SQL server uses the default JRE's trust store jre/lib/security/cacerts.

    Use hostNameInCertificate=yes to verify that DNS and SubjectAltName in the SSL certificate are the same.

    For trustStore=/my/own/trustStore.jks, do not use the default JRE's trust store jre/lib/security/cacert, use a separate one.

    The trustStorePassword=changeit is the password for the trust store.


**UrbanCode Deploy Agent** 

To add the protocol to UrbanCode Deploy agents using JMS or HTTPS to talk to the UrbanCode Deploy server:

-   Add new line `-Djdk.tls.client.protocols=TLSv1.2` in agent-home/bin/worker-args.conf.

Step running on UrbanCode Deploy agent:

-   Add new line `-Djdk.tls.client.protocols=TLSv1.2` to gent-home/conf/plugin-javaopts.conf.

**Parent topic:** [SSL configuration](../../com.udeploy.doc/topics/SSLinstall.md)

