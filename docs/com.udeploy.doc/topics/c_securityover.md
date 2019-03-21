# Security considerations for IBM UrbanCode Deploy

You can act to ensure that your installation is secure and set up user access controls.

-   [Enabling security during the installation process](c_securityover.md#EnablingSecurityInstall)
-   [Enabling secure communication between multiple applications](c_securityover.md#EnablingSecureCommunication)
-   [Ports, protocols, and services](c_securityover.md#PortsProtocolsAndServices)
-   [Keystores for SSL communication and for encrypting secure properties](c_securityover.md#SSLKeystores)
-   [Customizing your security settings](c_securityover.md#CustomizingYourSecuritySettings)
-   [Setting up user roles and access](c_securityover.md#SettingUpUserRolesAndAccess)
-   [Privacy policy considerations](c_securityover.md#Cookies)

## Enabling security during the installation process

During the installation process, by default the server is configured to use Secure Sockets Layer \(SSL\) for secure communication. The server is configured to use SSL in both manual and silent installations. In addition to SSL communication, role-based access controls are available that determine what actions a particular user can do.

In general, you configure security on the application server or the database server, not in HCL® UrbanCode™ Deploy. HCL UrbanCode Deploy communicates with the database by using the Java™ Database Connectivity \(JDBC\) provider on the application server.

To learn about configuring Lightweight Directory Access Protocol \(LDAP\) authentication, see [Authentication realms](../../com.udeploy.admin.doc/topics/security_auth.md).

## Installing a FIPS-compliant server

You can configure a Federal Information Processing Standards \(FIPS\) compliant server by specifying options at installation time. A FIPS-compliant server has certain limitations. See [Installing the server in interactive mode](../../com.udeploy.install.doc/topics/server_install_interactive.md).

## Enabling secure communication between multiple applications

You can use tokens to secure communications between products that integrate with HCL UrbanCode Deploy. To learn more about tokens, see [Tokens](../../com.udeploy.admin.doc/topics/security_token.md).

## Ports, protocols, and services

The following table shows the default port numbers for the server.

|Port type|Default port number|
|---------|-------------------|
|Incoming connections to the server web interface \(HTTP\)|8080|
|Incoming connections to the server web interface \(HTTPS\)|8443|
|Java Message Service \(JMS\)|7918|
|WebSocket agent|7919|
|Communication with the Rational® Common Licensing server|Port 27000 for the `lmrgd` daemon. The port numbers for the vendor daemon can change, but are typically between 27001 and 27009. See your Rational Common Licensing server for the active ports.|

The following table shows the default port numbers for the blueprint design server and engine.

**Note:** If you install the HCL UrbanCode Deploy server and the blueprint design server on the same computer, ensure that only one server uses port 8080 and port 8443.

|Port type|Default port number|
|---------|-------------------|
|Incoming connections to the blueprint designer web interface \(HTTP\)|8080|
|Incoming connections to the blueprint designer web interface \(HTTPS\)|8443|
|Incoming connections to the engine|8004, 8000, 8003, and RPC ports|
|Incoming connections to the cloud discovery service|7575|

The blueprint design server must also be able to create outgoing connections to cloud systems, the engine, the cloud discovery service, and the database. The communication with the Rational Common Licensing server uses port 27000 for the `lmrgd` daemon. The port numbers for the vendor daemon can change, but are typically between 27001 and 27009. See your Rational Common Licensing server for the active ports.

In most cases, the blueprint design server accesses the cloud discovery service on local port 7575, and no firewall rules are required. However, if the blueprint design server uses the host name of the machine, you may need to provide access to port 7575 on the firewall.

## Keystores for SSL communication and for encrypting secure properties

HCL UrbanCode Deploy supports multiple keystores, which support different security features. The following list describes the default keystores.

-   **tomcat.keystore**

    The certificate for SSL communication on the HTTPS port of the HCL® UrbanCode™ Deploy server is stored in the tomcat.keystore file.

-   **server.keystore**

    The certificate for SSL communication on the JMS port is stored in the server.keystore file. If mutual authentication is enabled, the identities of the server and agent computers are verified. If mutual authentication is disabled, then the server.keystore file is used only to encrypt network traffic. By default, mutual authentication is disabled.

    **Important:** 

    Mutual authentication is not needed with web agents, therefore is deprecated starting in HCL® UrbanCode™ Deploy version 7.0.0.

-   **encryption.keystore**

    The secret key that is used to encrypt and decrypt secure properties is stored in the encryption.keystore file. If you export applications and components that use secure properties to other HCL® UrbanCode™ Deploy servers, you must exchange the contents of this keystore between the servers. The secret key in the encryption.keystore file is randomly generated during installation. The password is stored in the `encryption.keystore.password` property, and its initial value is the same as the `server.keystore.password` property value.

-   **tomcat.keystore on the blueprint design server**

    The blueprint design server also has a keystore that is named tomcat.keystore. The blueprint design server keystore contains the certificate for SSL communication on the HTTPS port of the blueprint design server. The default location is server\_install/opt/tomcat/conf/tomcat.keystore, where server\_install is the installation folder of the blueprint design server.


For more information on keystores and certificates, see [Configuring SSL on Apache Tomcat and LDAP servers](ssl_config.md#).

## Customizing your security settings

The only user IDs that are created by default are admin for the server and ucdpadmin for the blueprint designer. To change the password for admin, in the server, click **Settings** \> **Authentication \(Users\)**. To change the password for ucdpadmin, click **Settings** \> **Users** and select the **Internal Authentication** authentication realm.

Failed login attempts are stored in the database. Except for the default admin password, all passwords are stored in encrypted form in the database. After you change the default admin password, it is also stored in encrypted form.

## Setting up user roles and access

You can create and delete users and add users to groups and teams in HCL UrbanCode Deploy. To learn more, see [Managing security](../../com.udeploy.admin.doc/topics/security_ch.md). On the server, the superuser account with special security privileges is admin. On the blueprint editor, the superuser account with special security privileges is ucdpadmin.

The HCL UrbanCode Deploy server and the blueprint designer have separate lists of users and teams.

## Privacy policy considerations

Depending on the configurations that are deployed, this software offering might use cookies that can help you to collect personally identifiable information. For information about this use of cookies, see the [Notices](notices.md) topic.

**Parent topic:** [Overview](../topics/c_node_overview.md)

