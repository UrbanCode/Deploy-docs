# Creating authentication realms for the blueprint designer

To allow users to log into the blueprint designer, you must create an authentication realm for it.

The blueprint design server supports several types of authentication realms.

**Note:** The authentication realms for the blueprint designer are separate from the authentication realms for the HCL® UrbanCode™ Deploy server. However, you can import users from HCL UrbanCode Deploy; see [Importing user accounts from HCL UrbanCode Deploy to the blueprint design server](security_realms_ucd.md). If you import users from your HCL UrbanCode Deploy server, you must import users before you connect the blueprint design server to the HCL UrbanCode Deploy server.

-   **[Importing user accounts from HCL UrbanCode Deploy to the blueprint design server](../../com.ibm.edt.doc/topics/security_realms_ucd.md)**  
You can use an authentication realm to import user accounts from an HCL UrbanCode Deploy server. Then, users can log in to the blueprint design server with the same accounts as the HCL UrbanCode Deploy server.
-   **[Creating LDAP authentication realms for the blueprint designer](../../com.ibm.edt.doc/topics/security_realms_ldap.md)**  
To create an authentication realm on the blueprint design server, specify where to store information about the users, such as internal storage on the blueprint design server or on an LDAP server.
-   **[Creating OpenStack identity service authentication realms for the blueprint designer](../../com.ibm.edt.doc/topics/security_realms_openstack.md)**  
You can use an authentication realm to import user accounts from an OpenStack server to the blueprint design server. You must specify the URL and account information for the Keystone identity service.
-   **[Creating SSO authentication realms for the blueprint designer](../../com.ibm.edt.doc/topics/security_realms_sso.md)**  
Create an authentication realm on the blueprint design server to interact with the single sign-on server.

**Parent topic:** [Configuring security for the blueprint design server](../../com.ibm.edt.doc/topics/security_ov.md)

