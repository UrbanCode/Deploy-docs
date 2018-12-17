# Importing user accounts from HCL UrbanCode Deploy to the blueprint design server

You can use an authentication realm to import user accounts from an HCL® UrbanCode™ Deploy server. Then, users can log in to the blueprint design server with the same accounts as the HCL UrbanCode Deploy server.

-   Importing accounts in this way requires HCL UrbanCode Deploy version 6.1.1.2 or later.
-   Obtain either a token or a user name and password for the HCL UrbanCode Deploy server.
-   On the HCL UrbanCode Deploy server, set permissions for the users, including giving the users access to components.

    **Note:** When a user logs in to the blueprint designer with an account from HCL UrbanCode Deploy, that user sees only the components that they could see if they logged in to the HCL UrbanCode Deploy server. If a user logs in with account from a different authentication realm, that user sees the components that are associated with the token or user account that is on the **System Settings** page.


1.   Log in to the blueprint designer as a user with the following **System** permissions: 
    -   Configure Security
    -   Manage Users & Groups
2.  Click **Settings** \> **Users**.
3.  Click **Create New Realm**. 
4.  Specify a name and description for the new authentication realm.
5.  In the **Allowed Login Attempts** list, specify the number of times that a user can attempt to log in before the account is locked.A blank value means that an unlimited number of attempts are allowed.
6.  In the **Type** list, select **UrbanCode Deploy**.
7.  In the **UrbanCode Server URL** field, specify the full URL of the server, such as `https://ucdserver.example.com:8443`. 
8.  To authenticate with a token, select **Token Based Authentication** and specify the token in the **Token** field. 
9.  To authenticate with a user name and password, clear **Token Based Authentication** and specify the user name and password. 
10. Click **Save**.The new realm opens, showing the table of users.
11. Click **Import Users**, and then click **Import** to import users from the authentication realm.

Now users can use the same credentials on the HCL UrbanCode Deploy server and on the blueprint design server.

Add the users to groups and teams. You must add users to teams to give the users permission to work with blueprints and cloud resources.

