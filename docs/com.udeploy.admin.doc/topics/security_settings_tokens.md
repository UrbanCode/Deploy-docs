# Token expiration settings

Tokens provide authorization for agents, agent relays, users, and external systems or applications from the server. Agents use tokens when they run process steps and communicate with the HCL® UrbanCode™ Deploy server and external services. In the **Security** settings area you can set time limits for three tokens types.Two tokens types work with plug-ins that enable discovering and applying configurations. The third type is used when component versions are automatically imported. You can set the how much time elapses before the token expires.

The tokens are generated automatically when the steps are run. The first three tokens use the built-in UC Auto Configure, UC Auto Discovery, and UC Version Import users and their permissions. The plug-in token has the permissions of the user who requests the process that plug-in runs from. These tokens are the same as those that you can create in the user interface and a command-line interface. See [Tokens](security_token.md#). Go to the [IBM devloperWorks website](https://developer.ibm.com/urbancode/plugins/) to access plug-ins that work with HCL UrbanCode Deploy and provide steps that create these tokens.

To access the **Security** settings area, click **Settings**, click **System Settings**, and then scroll down.

You can specify these expiration delays for tokens:

-   **Discovery Auth Token Expiration Delay \(seconds\)**

    Set the expiration delay in seconds for authorization tokens that are created for autodiscovery steps. You must specify at least 300 seconds. Typically, discoveries do not require more than 300 seconds \(5 minutes\).

-   **Configure Auth Token Expiration Delay \(seconds\)**

    Set the expiration delay in seconds for authorization tokens that are created for autoconfiguration steps. You must specify at least 300 seconds. Be sure to specify sufficient time for autoconfiguration, because the step processes stop when the token expires.

-   **Version Import Auth Token Expiration Delay \(seconds\)**

    Set the expiration delay in seconds for authorization tokens that are created for version import steps. You must specify at least 300 seconds. The time required to import versions depends on component size.

-   **Plugin Step Auth Token Expiration**

    Set the expiration delay in seconds for authorization tokens that are created for plug-in steps. You must specify at least 300 seconds. The time required to import versions depends on component size.


**Parent topic:** [Tokens](../../com.udeploy.admin.doc/topics/security_token.md)

