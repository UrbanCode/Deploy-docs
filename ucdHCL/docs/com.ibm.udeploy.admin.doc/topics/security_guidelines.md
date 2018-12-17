# Guidelines for setting up server security

Although there is no single best way to set up security for the server, the following steps are sufficient in most cases.

If you are upgrading from an earlier version, see [Migrating security settings](../../com.ibm.udeploy.install.doc/topics/upgrade_security.md).

1.   Create an authorization realm for the server. Authorization realms are used by authentication realms to associate users with groups and to determine user access. HCL UrbanCode Deploy includes an internal database for storing security information and integration with the Lightweight Directory Access Protocol \(LDAP\). LDAP is a widely used protocol for accessing distributed directory information over IP networks. 
2.   Create an authentication realm for the server. The authentication realm is used to determine a user's identity within an authorization realm. 
3.   Create security types. Security types classify artifacts such as environments and components by level of security.
4.   Create roles and define permissions for them. 
5.  Create and import users and groups.
6.   Create teams, and assign users and groups to them. 
7.   Assign elements, such as applications and environments, to teams. After you complete the preceding steps, users on the associated teams have access to those elements. The access rights that each user has for those elements depend on the user's role within that team.

**Parent topic:** [Managing security](../../com.ibm.udeploy.admin.doc/topics/security_ch.md)

