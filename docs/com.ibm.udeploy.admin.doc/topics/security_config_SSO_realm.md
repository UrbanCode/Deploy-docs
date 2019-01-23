# Creating an SSO authorization realm

A single sign-on \(SSO\) authorization realm uses an external server for authorization.

1.   On the server, click **Settings** \> **Authorization \(Groups\)** \> **Create Authorization Realm**. The Create Authorization Realm dialog box opens. 
2.   Enter a name in the **Name** field. 
3.   Ensure that **SSO** is selected in the **Type** list. 
4.   Specify these parameters: 

    |Field|Description|
    |-----|-----------|
    |**Groups Header**|The name of the SSO server parameter that contains the list of groups to which the user belongs.|
    |**Groups Delimiter**|The string that delimits values that are found in the group header. Regular expression special characters must be escaped with the backslash \(\\\) character.|
    |**Groups Regex**|The regular expression that is used to parse the values in the group header. If specified, only the first matching group is used. If left unspecified, all values in the group header are used.|

    The values in the group header that match the search criteria are used to create HCL® UrbanCode™ Deploy groups into which the user is placed.


**Parent topic:** [Authorization realms](../../com.ibm.udeploy.admin.doc/topics/security_config.md)

