# Creating OpenStack identity service authentication realms for the blueprint designer

You can use an authentication realm to import user accounts from an OpenStack server to the blueprint design server. You must specify the URL and account information for the Keystone identity service.

Install an engine for the OpenStack server. See [Installing the engine](../../com.udeploy.install.doc/topics/install_engine.md).

These steps assume that you have user accounts on the OpenStack server and are managing user authentication on that server. To manage authentication through another source, create functional IDs on the OpenStack server and add those IDs to a cloud project, as described in [Creating cloud projects for the blueprint designer](security_projects.md).

If your OpenStack identity service that uses API v3 contains multiple domains, you must create an authentication realm for each domain.

1.   Log in to the blueprint designer as a user with the following **System** permissions: 
    -   Configure Security
    -   Manage Users & Groups
2.  Click **Settings** \> **Users**.
3.  Click **Create New Realm**. 
4.   Specify a name and description for the new authentication realm. 

    **Note:** If your OpenStack identity service uses API v3, include the domain name in the authentication realm.

5.  In the **Allowed Login Attempts** list, specify the number of times that a user can attempt to log in before the account is locked.A blank value means that an unlimited number of attempts are allowed.
6.  In the **Type** list, select **OpenStack Identity Service**.
7.   In the **OpenStack Identity Service** section, in the **Identity URL** field, specify the location of the identity service, such as `https://example.com:5000/v2.0` or `https://example.com:5000/v3`. 
8.   Specify the Heat orchestration engine to use. 
9.   Specify the administrator user name, password, and tenant or project for the OpenStack server. 

    **Note:** If your OpenStack identity service uses API v3, specify the administrator user name, password, and tenant or project for a domain on the OpenStack server.

    **Note:** This administrator user must be a member of each tenant that you want to use.

10.  If your OpenStack identity service uses API v3, enter the domain that the administrator user that you specified belongs to. If your OpenStack identity service uses API v2.0, accept the default value.
11. Click **Save**.The new realm opens, showing the table of users.
12.  Click **Users**, and then click **Import User** to import users from the authentication realm. If your OpenStack identity service uses API v2.0, all users on the server are imported. If your OpenStack identity service uses API v3, only the users from the specified domain are imported.

    **Note:** If you cannot import users, click **Edit**, and then click **Test Connection** to view the failure details.


The blueprint design server creates an authentication realm and cloud connection based on the cloud information that you specified. The blueprint design server also creates a cloud project for each tenant or project on the cloud.

-   Add the users to groups and teams. You must add users to teams to give the users permission to work with blueprints and cloud resources.
-   Add the cloud projects to teams.

