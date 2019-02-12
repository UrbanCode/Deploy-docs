# Creating SSO authentication realms for the blueprint designer

Create an authentication realm on the blueprint design server to interact with the single sign-on server.

1.   Log in to the blueprint designer as a user with the following **System** permissions: 
    -   Configure Security
    -   Manage Users & Groups
2.  Click **Settings** \> **Users**.
3.  Click **Create New Realm**. 
4.  Specify a name and description for the new authentication realm.
5.  In the **Allowed Login Attempts** list, specify the number of times that a user can attempt to log in before the account is locked.A blank value means that an unlimited number of attempts are allowed.
6.   In the **Type** list, select **Single Sign-On**. 
7.   In the **Single Sign-On** section, specify the properties in the following table. 

    |Field|Description|
    |-----|-----------|
    |**User Header Name**|The header that contains the username.|
    |**Email Header Name**|The header that contains the user's email address.|
    |**Logout URL**|The URL where the users are redirected after they log out of HCL® UrbanCode™ Deploy.|
    |**Full Name Header Name**|The header that contains the user's full name.|

8.   In the **Group** section, specify the properties in the following table. 

    |Field|Description|
    |-----|-----------|
    |**Groups Header**|The header that contains the list of groups to which the user belongs. Separate headers with the character indicated in the **Groups Delimiter** field.|
    |**Groups Delimiter**|The string that delimits values that are found in the groups header. Regular expression special characters must be escaped with the `\` character.|
    |**Groups Regex**|The regular expression that is used to find the groups in the header value. If you specify a capturing group with parentheses, the first matching regex value per delimited string is captured. If no capturing group is specified, then the whole delimited string is captured.|

9.   Click **Save**. 

-   Add the users to the realm and then add them to teams. You must add users to teams to give the users permission to work with blueprints.
-   Configure how the users authenticate to the cloud. See [Setting up access to clouds in the blueprint designer](security_auth_bds.md).

**Parent topic:** [Creating authentication realms for the blueprint designer](../../com.edt.doc/topics/security_realms_create.md)

