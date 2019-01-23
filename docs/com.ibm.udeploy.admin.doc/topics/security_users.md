# Configuring blueprint design server users

You can import users from an authentication realm or create them manually on the blueprint design server. Then, you can add the users to groups, roles, and teams.

Rather than having its own list of users, the blueprint design server imports accounts from authentication realms, including OpenStack Keystone services and LDAP servers.

The blueprint design server includes an internal authentication realm to contain users such as the administrator.

1.   If you are importing users from a cloud system or an LDAP server, create an authentication realm from that cloud or LDAP server and import the users from that authentication realm to the blueprint design server. See [Setting up access to clouds in the blueprint designer](security_auth_bds.md).
2.  If you are adding users manually, open the `Internal Authentication` authentication realm, click **Create User**, and specify the information for the user.
3.  Add users to groups on the **Group** tab. 

Add the users to groups and teams. You must add users to teams to give the users permission to work with blueprints and cloud resources.

