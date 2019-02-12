# Importing LDAP users

On the server, LDAP authentication realm users are imported from external LDAP systems.

LDAP authentication realms are searched whenever an unknown user attempts to log on to the server. If the user is found, a corresponding record is created in HCL® UrbanCode™ Deploy. Because LDAP users cannot be assigned to groups and teams until they have corresponding HCL UrbanCode Deploy accounts, you can import users directly from LDAP systems.

1.   On the server, click **Settings** \> **Authentication \(Users\)** \> **selected LDAP realm** \> **Import User**. 
2.   In the Import Users dialog box, enter a name or pattern to search in the **Username or Pattern** field. The asterisk character \(`*`\) can be used as a wildcard in the pattern. If you use an asterisk by itself, you import all users for the selected LDAP realm.
3.   Click **Save** to start the search. 

**Parent topic:** [Authentication realms](../../com.udeploy.admin.doc/topics/security_auth.md)

