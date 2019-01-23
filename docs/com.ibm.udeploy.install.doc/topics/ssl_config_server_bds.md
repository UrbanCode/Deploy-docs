# Configuring SSL security on Apache Tomcat for the blueprint design server

The steps for configuring secure HTTP connections with the blueprint design server are similar to the steps for any Java™ Platform, Enterprise Edition server.

To set up SSL security, you must have a certificate for the blueprint design server. If you use certificates that are self-signed or certificates that are issued by a certificate authority that is not trusted, you must import these certificates into the trust store. A trust store contains trusted certificates from servers and certificate authorities. Import the self-signed certificates, certificate authority certificates, and intermediate certificate authority certificates to the JRE\_install/jre/lib/security/cacerts file. For an example of importing a certificate to a trust store, see the [Importing the Certificate Reply from the CA](http://www.ibm.com/support/knowledgecenter/SSYKE2_7.0.0/com.ibm.java.security.component.70.doc/security-component/keytoolDocs/ex_importcertreply.html) topic in the IBM® SDK, Java Technology Edition help.

In the case of LDAP servers, SSL certificates must have valid chains of authority. If you use your own certificate authority, add that certificate authority to the local trust store.

Because the blueprint design server runs on Apache Tomcat, you can refer to the instructions for configuring security on Tomcat [on the Apache Tomcat website](http://tomcat.apache.org/tomcat-6.0-doc/ssl-howto.html#Certificates). You can enable SSL security for Apache Tomcat when you install the blueprint design server. If you enable SSL security during installation, a self-signed certificate is generated and added to the tomcat.keystore file. The common name \(CN\) in the self-signed certificate is set to 0.0.0.0.

**Note:** The presence of a self-signed certificate is flagged as a warning by many web browsers when you connect to a blueprint design server that uses a self-signed certificate in the tomcat.keystore file.

1.  Setting up SSL security for the blueprint design server involves these general steps:
2.   Transfer the files for the certificate to the computer that hosts the blueprint design server. 
3.   Add the certificate to the blueprint design server keystore. The blueprint design server has a default keystore in the server\_install/opt/tomcat/conf/tomcat.keystore file. The default password for this keystore is `changeit`.
4.   Restart the blueprint design server. 
5.   Similarly, add the same certificate to the keystore of each agent and agent relay. For example, the default location of an agent keystore is agent\_install/conf/agent.keystore.
6.   To configure secure communication between the blueprint design server and an LDAP server, add the LDAP server certificate to the JRE\_install/jre/lib/security/cacerts file. This file is on the blueprint design server. Use the installation folder of the JRE for JRE\_install. 

