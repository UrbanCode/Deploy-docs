# Creating an LDAP authorization realm

An LDAP authorization realm defines how to use an external LDAP server for group authorization.

You must have the URL of the external LDAP server that you want to use for authorization.

An LDAP authorization realm defines how to search user groups. Typically, authorization realms work in tandem with LDAP authentication realms. When unknown users attempts to log on, an external LDAP server is used to authenticate them by using the authorization and authentication realms that you define. Administrators can also use the authorization and authentication realms to import users. You might want to import users and assign them to teams before their first logon attempt. When you import users, you can supply additional parameters to further refine the search. For more information, see [Importing LDAP users](security_user_import.md).

To create an LDAP authorization realm, you identify the URL of the LDAP server, and define a role-based search. If you use an LDAP authentication realm, you do not need to define a user-based search. If you use an SSO authentication realm, you must also define a user-based search.

1.   On the server, click **Settings** \> **Authorization \(Groups\)** \> **Create Authorization Realm**. The Create Authorization Realm dialog box opens. 
2.   In the **Name** field, enter a realm name. 
3.   In the **Type** list, select **LDAP or Active Directory**. 
4.   In the **LDAP URL** field, enter the URL of the LDAP server. Separate multiple servers by commas. For example, `ldap://ldap_server.my_domain.com:389,ldap://ldap_server.my_domain2.com:389`.
5.   Define a role-based search by completing one of these steps: 
    1.   If you want to reference roles by members, select **Roles in LDAP reference their members; look up group membership by searching for roles**, and then specify the following parameters: 

        |Field|Description|
        |-----|-----------|
        |**Group Search Base**|The directory that is used for group searches, such as `ou=employees,dc=mydomain,dc=com`.|
        |**Group Search Filter**|The LDAP filter expression that is used when you search for user entries. The user name replaces the \{1\} variable in the search pattern and the full user distinguished name \(DN\) replaces the \{0\} variable, for example, `(&(uniqueMember={0})(cn=BSO*))`.|
        |**Group Name**|The name of the entry that contains the users' group names in the directory entries that are returned by the group search. If this entry is not specified, no group search runs. For example, enter `cn`.|
        |**Search Group Subtree**|Subtrees \(if any\) are searched. If the item is not selected, the search is limited to the group search base.|

        The values in the **Group Search Base** and **Search Group Subtree** fields define the scope of the search. Within the scope, groups that match the group search filter are searched. The value in the **Group Name** field specifies the LDAP attribute that contains the group name.

    2.   If you want to reference roles by user attributes, select **User roles are defined as an attribute on that user; look up group membership using this attribute**, and then, in the **User Group Attribute** field, specify the attribute that contains group names in the user directory entry. If user groups are defined in LDAP as an attribute of the user, you must use the Group Attribute configuration.
6.   Define a user-based search by completing one of these steps: 

    **Note:** If you plan to use an SSO authentication realm with this authorization realm, you must define a user-based search. If you plan to use an LDAP authentication realm, you can skip this step.

    1.   If user records exist in multiple directories, select **LDAP users may exist in many directories; search across LDAP using a criteria.**, and then specify these parameters: 

        |Field|Description|
        |-----|-----------|
        |**User Search Base**|The starting directory for the search, such as `ou=employees,dc=mydomain,dc=com`.|
        |**User Search Filter**|The LDAP filter expression that is used when searching for user entries. The user name replaces the \{0\} variable in the search pattern, for example, `uid={0}`.|
        |**Search Group Subtree**|Subtrees \(if any\) are searched. If the item is not selected, the search is limited to the search base.|

    2.   If users exist in a single directory, select **LDAP users exist in a single directory; use a pattern to create the DN for users**, and then, in the **User DN Pattern** field, specify the name. The name is substituted in place of \{0\} in the search pattern, such as `cn=[0],ou=employees,dc=mydomain,dc=com`.
7.   Secure the communication between the LDAP server and the HCL® UrbanCode™ Deploy server as described in [Configuring SSL on Apache Tomcat and LDAP servers](../../com.ibm.udeploy.doc/topics/ssl_config.md). 
8.   Set the length of time for the server to wait for a response from the LDAP server. On the server, in the installed.properties file, set the property com.sun.jndi.ldap.read.timeout to the timeout period in milliseconds. Then, restart the server. 

The first time an unknown user attempts to log on, LDAP authorization realms are searched in an attempt to identify the user. If the user is found, a corresponding user ID is created in HCL UrbanCode Deploy. In addition, if the user is part of an LDAP group, that group is imported too.

**Parent topic:** [Authorization realms](../../com.ibm.udeploy.admin.doc/topics/security_config.md)

