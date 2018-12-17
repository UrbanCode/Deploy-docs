# Accessing HCL UrbanCode Deploy

You can access the server and the blueprint designer with a web browser.

-   Start the server. See [Starting and stopping the server](run_server.md).
-   Start the blueprint design server. See [Starting the blueprint designer, cloud discovery service, and engine](start_patterns.md#)

1.   Open a web browser and go to the server host name that you configured during installation. The installation log shows the complete URL for the server. The default URL is `https://hostname:port`, where `hostname` host name of the computer on which the server is running and `port` is the HTTPS port that you used when you installed the server. The default HTTPS port is 8443.
2.   Log on to the server by using the default credentials. The default user name is admin, and you specified the password when you installed the server. You can change these credentials later by using the Settings tab on the HCL® UrbanCode™ Deploy web application. See [Server settings and configuration](../../com.ibm.udeploy.doc/topics/settings_ch.md) 
3.   Open a web browser and go to the blueprint designer host name that you configured during installation. The installation log shows the complete URL for the blueprint design server. The default URL is `https://hostname:port/landscaper` , where `hostname` is the host name of the blueprint design server, and `port` is the HTTP port that you specified when you installed the blueprint design server. The default HTTPS port is 8443.
4.   Log on to the blueprint design server by using the default credentials. The default administrator user name is `ucdpadmin`, and the default password is `ucdpadmin`. You can change these credentials later by using the Settings menu on the blueprint designer. See [Configuring security for the blueprint design server](../../com.ibm.udeploy.admin.doc/topics/security_ov.md) 

If you set the server to use secure connections, your web browser might show a security warning that says that the connection is not secure. This warning appears because the server does not have a trusted certificate. See [Configuring SSL on Apache Tomcat and LDAP servers](../../com.ibm.udeploy.doc/topics/ssl_config.md).

