# Creating authentication realms

To create an authentication realm on the server, specify where to store information about the users, such as internal storage on the server, a single sign-on service, or on an LDAP server.

1.   On the server, click **Settings** \> **Authentication \(Users\)** \> **Create Realm**. The Create Authentication Realm pane opens. 
2.   Enter a name, description. 
3.   Enter the number of user login attempts to accept in the **Allowed Login Attempts** field. A blank value means that an unlimited number of attempts are allowed. If a user exceeds the attempt limit, use the **Unlock User** action on the Authentication page to unlock the user.
4.   Select the authentication realm type from the **Type** list. The available types in the list are as follows: **LDAP or Active Directory**, **Single Sign-on** \(SSO\), and **Internal Storage**. If you select **Internal Storage**, no additional parameters are needed. If you select **LDAP or Active Directory**, or **Single Sign-on**, specify the following parameters:

    |Field|Type|Description|
    |-----|----|-----------|
    |LDAP URL|LDAP|The URL of the LDAP server that begins with `ldap://` or `ldaps://`. You can provide more than one URL, separated by spaces. If you provide more than one URL, the server tries the URLs one at a time until one succeeds.|
    |Search Anonymously|LDAP|Selected if LDAP accepts anonymous queries. If this check box is cleared, specify the LDAP search connection DN and associated password. This check box is selected by default.|
    |Search Connection DN|LDAP|Complete LDAP distinguished name to search. This parameter is used if the **Search Anonymously** check box is cleared.|
    |Search Connection Password|LDAP|Password that is used for LDAP searches. This parameter is used with the value in the **Search Connection DN** field.|
    |Specify how to search LDAP|LDAP|Specifies how LDAP is searched. If users exist in multiple directories, select **LDAP users may exist in many directories; search across LDAP using a criteria**; otherwise, select **LDAP users exist in a single directory; use a pattern to create the DN for users.**. Depending on the selection, more fields are displayed.|
    |User Search Base|LDAP|When you search multiple directories, specify the starting directory that is used for searches, such as `ou=employees,dc=mydomain,dc=com`.|
    |User Search Filter|LDAP|The LDAP filter expression to use when you search for group entries, such as `(&(|(mail={0})(cn={0}))(objectclass=ePerson))`. The user name replaces the \{1\} variable in the search pattern, and the full user DN replaces the \{0\} variable. If the value is not part of the DN pattern, enclose the value in parenthesis, for example, `(accountName={0})`. For more information, see the help information for your LDAP server and look for information about creating user search filters.|
    |Search User Subtree|LDAP|When you search multiple directories, select this check box to search directories below the base directory.|
    |User DN Pattern|LDAP|When you search a single directory, the name is substituted in place of 0 in the pattern, for example, `cn={0},ou=employees,dc=yourcompany,dc=com`.|
    |Name Attribute|LDAP|Contains the user name in LDAP.|
    |Email Attribute|LDAP|Contains the user email address in LDAP.|
    |User Header Name|SSO|The header that contains the list of users.|
    |Email Header Name|SSO|A header that contains the list of user email addresses.|
    |Logout URL|SSO|The URL where the users are redirected after they log out of HCL® UrbanCode™ Deploy.|

5.   Select the authorization realm from the **Authorization Realm** list. The internal security realm is initially available. See [Authorization realms](security_config.md#).

    **Note:** If you use an LDAP authentication realm with an LDAP authorization realm, the settings on this authentication realm override the settings on the LDAP authorization realm. If you use an SSO authentication realm with an LDAP authorization realm, you must specify connection settings on the LDAP authorization realm.


When new users log on to the server and use their LDAP or SSO credentials, they are listed on the **Authentication** tab. In most cases, do not manage user passwords or remove users from the list. If an active user is removed from HCL UrbanCode Deploy, they are still able to log on to the server while their LDAP credentials are valid.

**Parent topic:** [Authentication realms](../../com.udeploy.admin.doc/topics/security_auth.md)

