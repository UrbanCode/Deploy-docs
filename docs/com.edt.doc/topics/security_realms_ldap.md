# Creating LDAP authentication realms for the blueprint designer

To create an authentication realm on the blueprint design server, specify where to store information about the users, such as internal storage on the blueprint design server or on an LDAP server.

1.   Log in to the blueprint designer as a user with the following **System** permissions: 
    -   Configure Security
    -   Manage Users & Groups
2.  Click **Settings** \> **Users**.
3.  Click **Create New Realm**. 
4.  Specify a name and description for the new authentication realm.
5.  In the **Allowed Login Attempts** list, specify the number of times that a user can attempt to log in before the account is locked.A blank value means that an unlimited number of attempts are allowed.
6.  In the **Type** list, select **LDAP or Active Directory**.
7.  If the LDAP server requires authentication to search the directory, clear the **Search Anonymously** check box.
8.  In the **LDAP URL** field, specify the URL for the server.The URL begins with `ldap://` or `ldaps://`. To connect to more than one server, separate each URL with a space.
9.  In the **User** section, specify the properties in the following table.

    |Field|Description|
    |-----|-----------|
    |**Search Method**|If users exist in multiple directories, select **Criteria-based search across multiple directories**. Otherwise, select **Pattern to create the DN for users in a single directory**.|
    |**User Name Attribute**|The attribute name that contains the user name, such as `cn` or `name`.|
    |**User Search Base**|When you search multiple directories, specify the starting directory that is used for searches, such as `ou=employees,dc=mydomain,dc=com`.|
    |**Email Attribute**|The attribute name that contains the email address, such as `email` or `mail`.|
    |**User Search Filter**|The LDAP filter expression to use when you search for group entries, such as `(&(|(mail={0})(cn={0}))(objectclass=ePerson))`. The user name replaces the \{1\} variable in the search pattern, and the full user DN replaces the \{0\} variable. If the value is not part of the DN pattern, enclose the value in parenthesis, for example, `(accountName={0})`. For more information, see the help information for your LDAP server and look for information about creating user search filters.|
    |**Search User Subtree**|When you search multiple directories, select this check box to search directories below the base directory.|

10. In the **Group** section, specify the properties in the following table.

    |Field|Description|
    |-----|-----------|
    |**Search Method**|To search for groups according to roles, select **Look up group membership by searching for roles**. To search for groups according to an attribute, select **Look up group membership using this attribute**, and specify the attribute in the **User Group Attribute** field.|
    |**User Group Attribute**|Specify the attribute that contains group names. This field is available only if you select **Look up group membership using this attribute**.|
    |**Group Search Base**|This field is available only if you select **Look up group membership by searching for roles**.|
    |**Group Search Filter**|Specify the LDAP filter expression for groups. You can use the `{0}` variable to represent the full user DN and the `{1}` variable to represent the user name. This field is available only if you select **Look up group membership by searching for roles**.|
    |**Group Name**|Specify the name of the entry that contains the user group names. This field is available only if you select **Look up group membership by searching for roles**.|
    |**Search Group Subtree**|Select this check box to search the full subtree for groups. This field is available only if you select **Look up group membership by searching for roles**.|

11. Click **Save**.

-   Add the users to groups and teams. You must add users to teams to give the users permission to work with blueprints and cloud resources.
-   Configure how the users authenticate to the cloud. See [Setting up access to clouds in the blueprint designer](security_auth_bds.md).

**Parent topic:** [Creating authentication realms for the blueprint designer](../../com.edt.doc/topics/security_realms_create.md)

