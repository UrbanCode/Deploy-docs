# Authorization realms

Use the Authorization Realms pane to create authorization realms and user groups for the server. Groups can be imported from external systems, such as LDAP.

The available authorization realms for the server are as follows:

-   **Internal Storage**

    Uses internal role management. The default authorization realm \(Internal Security\) is of this type.

-   **LDAP or Active Directory**

    Uses external LDAP role management.

-   **SSO**

    Provides single sign-on authorization.


-   **[Creating an internal storage authorization realm](../../com.ibm.udeploy.admin.doc/topics/security_config_internal_realm.md)**  
Internal storage realms do not retrieve users from any external source. Instead, you add users to internal storage authorization realms manually.
-   **[Creating an LDAP authorization realm](../../com.ibm.udeploy.admin.doc/topics/security_config_ldap_realm.md)**  
An LDAP authorization realm defines how to use an external LDAP server for group authorization.
-   **[Creating an SSO authorization realm](../../com.ibm.udeploy.admin.doc/topics/security_config_SSO_realm.md)**  
A single sign-on \(SSO\) authorization realm uses an external server for authorization.
-   **[Creating groups manually](../../com.ibm.udeploy.admin.doc/topics/security_groups.md)**  
Groups are logical containers that are mechanisms that grant permissions to multiple users; members automatically share a group's permissions. Only authorization realms of the internal storage type can have manually created groups. Others types, such as LDAP, import groups cannot have manually created groups.
-   **[Adding users to groups manually](../../com.ibm.udeploy.admin.doc/topics/security_groupsAddUsers.md)**  
Authorization realms of the internal storage type can have manually created users. Others types, such as LDAP, import user groups cannot have manually created users.

**Parent topic:** [Managing security](../../com.ibm.udeploy.admin.doc/topics/security_ch.md)

