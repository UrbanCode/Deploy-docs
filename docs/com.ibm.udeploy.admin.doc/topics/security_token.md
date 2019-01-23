# Tokens

Tokens provide authorization for agents, agent relays, users, and external systems or applications from the server. Agents use tokens when they run process steps and communicate with the HCL® UrbanCode™ Deploy server and external services.

Users can use tokens with the command-line interface \(CLI\) client instead of supplying a user name and password in certain situations. For information, see [Command-line client \(CLI\) reference](../../com.ibm.udeploy.reference.doc/topics/cli_ch.md).

Follow these steps to create a token. You can also create a token through the CLI; see [createAuthToken](../../com.ibm.udeploy.api.doc/topics/udclient_createauthtoken.md).

1.  Log in as a user with the "Manage Security" permission. See [Setting server configuration security](security_system.md).
2.  On the server, click **Settings** \> **Tokens** \> **Create Token**. The Create Token dialog box.
3.  From the **User** list, select the user for the token. You can limit the actions available to the token by applying a token restriction to it. For information about creating and applying token restrictions, see [Restricting authentication tokens](security_token_restrict.md).

    **Note:** 

    If you are using the token to integrate with IBM® UrbanCode Release, you must specify the administrator.

    If the token is for an agent relay that is intended to use component version replication, the user must have a role that has the Read Artifact Set List permission. For information about the Read Artifact Set List permission, see [Setting server configuration security](security_system.md#).

4.  Specify the expiration date and time.
5.  To limit the use of the token to certain IP addresses, specify one or more IPv4 addresses in CIDR notation in the **Allowed IPs** field, such as `10.15.10.0/24`.

    **Note:** If you are using clustered servers as described in [Setting up high-availability clusters](../../com.ibm.udeploy.doc/topics/server_install_clustered.md), leave this field blank.

6.  Click **Save**.

    **Important:** The token is shown only one time after you create it. Copy the token immediately, because you cannot see it again.


Tokens can be used immediately after they are created. You can revoke a token at any time by clicking **Delete** in the **Actions** column.

-   **[Restricting authentication tokens](../../com.ibm.udeploy.admin.doc/topics/security_token_restrict.md)**  
Limit authentication token actions by applying token restrictions to process plug-in steps.
-   **[Token expiration settings](../../com.ibm.udeploy.admin.doc/topics/security_settings_tokens.md)**  
Tokens provide authorization for agents, agent relays, users, and external systems or applications from the server. Agents use tokens when they run process steps and communicate with the HCL UrbanCode Deploy server and external services. In the **Security** settings area you can set time limits for three tokens types.
-   **[Updating the agent relay authentication token password](../../com.ibm.udeploy.admin.doc/topics/security_token_update.md)**  
The authentication token password for the agent relay is specified during installation of the agent relay. You can update the authentication token and provide a password for the token by updating the agent relay properties file.

**Parent topic:** [Managing security](../../com.ibm.udeploy.admin.doc/topics/security_ch.md)

