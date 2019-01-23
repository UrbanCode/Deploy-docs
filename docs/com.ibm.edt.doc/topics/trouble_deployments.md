# Troubleshooting deployments

If you are having trouble with provisioning a blueprint, here are some things that might help.

-   **Timeout errors**

    -   Timeout errors can mean that an agent in the new environment cannot contact the HCL® UrbanCode™ Deploy server. Log in to the provisioned instance to see whether you can ping the HCL® UrbanCode™ Deploy server.
    -   This error can also mean that the cloud took too long to download component artifacts, to obtain data from HCL® UrbanCode™ Deploy server, or to run component processes. Increase the timeout period in the agent\_timeout, ucd\_client\_timeout, and component\_process\_timeout properties. Ensure that the sum of the periods in the agent\_timeout and component\_process\_timeout properties is smaller than the value of the Timeout in Mins field in the cloud settings.
    -   Ensure that the blueprint design server can connect to the cloud. You can verify the connection path with the curl or telnet commands. For example, make sure that no firewall, proxy, or security settings prevent communication between the blueprint design server and the cloud.
-   **Keystone token timeout errors**

    If the blueprint takes longer to provision than the amount of time that the Keystone authentication token is valid, the following error is displayed:

    ```
    Unauthorized:  resources.resource\_type:  The request you have made requires authentication.  (HTTP 401)
    ```

    To provision the blueprint, increase the duration of the Keystone token.

    1.  Stop the Keystone service. If you use a Kilo-level engine, including an engine that was provided with HCL® UrbanCode™ Deploy version 6.2.1.1 or later, run this command:

        ```
        systemctl stop openstack-keystone.service
        ```

    2.  Increase the token timeout value by increasing the value of the expiration parameter. Open the /etc/keystone/keystone.conf file and set a new, larger value for the expiration parameter. The value of the expiration is the amount of time in seconds that the Keystone token is valid.
    3.  Start the Keystone service. If you use a Kilo-level engine, including an engine that was provided with HCL® UrbanCode™ Deploy version 6.2.1.1 or later, run this command:

        ```
        systemctl start openstack-keystone.service
        ```

    4.  Provision the blueprint.
-   **Accessing blueprints**

    If you are trying to create an environment from a blueprint and the blueprint is not visible, make sure that the user name in the blueprint designer integration can access the blueprint. See [Connecting the blueprint design server to the server](../../com.ibm.udeploy.doc/topics/ucdp_integrate.md).

-   **Secure connections between engines and the blueprint design server**

    If you provision an environment from a blueprint that contains a nested blueprint, the engine must access that nested blueprint during the provisioning process. In this case, the engine uses the URL in the configuration file to access the nested blueprint, as in this configuration file example:

    ```
    resource_registry:
      UC::Blueprint::NestedBlueprint: https://designserver.example.com:8443/
        landscaper/rest/orchestration/blueprints/
        jsmith_00000000_0000_0000_0000_000000000002/default/
        NestedBlueprint/NestedBlueprint.yaml
      OS::Nova::Server : IBM::EC2::Server
      OS::Cinder::Volume : IBM::EC2::Volume
    ```

    In this example, the URL of the nested blueprint uses HTTPS. If you try to provision an environment from this blueprint and the engine is not configured for secure connections to the blueprint design server, you see this error:

    ```
    HT-EA96E26 HT-EA96E26 HT-64408AE Message objects do not support str() because they may contain non-ascii characters. Please use unicode() or translate() instead.
    ```

    To resolve this error, retrieve the security certificate from the blueprint design server and import that certificate into the computer that hosts the engine. You can also change the URL in the configuration file to use the HTTP protocol and the matching HTTP port for the blueprint design server.

-   **Deployment failures**

    To troubleshoot deployment errors, review the details of the application process request. In HCL® UrbanCode™ Deploy, click **Application** \> **application\_name** \> **History**, and then in the same row as your request, click **View Request**. Expand the failed step, and by the virtual image that was provisioned by the blueprint, click **Output log**.

    If the environment does not appear on the HCL® UrbanCode™ Deploy server or on the blueprint designer, check the blueprint design server logs for errors. You can also run the command `heat stack-list` to see whether the engine has a record of the environment. If so, you can use other Heat commands to get information about the environment.

    If your image is attached to multiple networks and you see a **Resource CREATE failed: NameError: resources.component\_name: Agent did not show up even after agent\_timeout\_value seconds!** error, change the naming pattern of the agent and provision the blueprint again. See step [4](blueprint_deploy_app.md#agent_name) of [Deploying applications with blueprints](blueprint_deploy_app.md#).

    If you provision to SoftLayer® and see a **Resource CREATE failed: KeyError: resources.vm1: 'x-account-meta-temp-url-key'** error message, you must apply the master API key to the object storage for your SoftLayer® account. Either upgrade to version 6.2.1.2 or later of the blueprint designer or take the following steps:

    1.  From the SoftLayer® console, obtain the public **Authentication Endpoint** and **API Key** for the object storage.
    2.  To obtain a return token that contains the X-Auth-Token and X-Storage-Url parameters, from a console, run the following command:

        ```
        curl -i -H "X-Auth-User: username" -H "X-Auth-Key: API\_Key" public\_endpoint\_value
        ```

        In this command, the username value is the SoftLayer® user name of the user who provisions, and the API\_Key and public\_endpoint\_value values are obtained from the SoftLayer® console.

        This command returns the X-Auth-Token and X-Storage-Url values.

    3.  By using the X-Auth-Token and X-Storage-Url values, list the SoftLayer® containers and confirm that the X-Account-Meta-Temp-Url-Key parameter is listed. Run the following command:

        ```
        curl -i -H "X-Auth-Token: X-Auth-Token-value" X-Storage-Url-value
        ```

        If the X-Account-Meta-Temp-Url-Key parameter is not listed, then the **Resource CREATE failed: KeyError: resources.vm1: 'x-account-meta-temp-url-key'** is valid, and you cannot authorize the object storage account.

    4.  To associate the object storage credentials with your API key, run the following command:

        ```
        curl -i -H "X-Account-Meta-Temp-URL-Key: Secret-Key" -H "X-Auth-Token: X-Auth-Token" -X POST X-Storage-Url-value
        ```

        In this command, Secret-Key is an arbitrary secret key that is used for security purposes.

        If this command returns a value of 204, then the secret key was added to the object storage account.

    5.  To verify that the API key was applied to the object storage, run the following command:

        ```
        curl -i -H "X-Auth-Token: X-Auth-Token-value" X-Storage-Url-value
        ```

        If the X-Account-Meta-Temp-Url-Key is set to your Secret-Key value, the API key was applied to the object storage.

-   **Google Cloud Platform socket error**

    If you provision multiple components to Google Cloud Platform, you might see a runtime socket error that is similar to this error:

    ```
    RuntimeError: resources.tc_2: Second simultaneous read on fileno 15 detected. Unless you really know what you're doing, make sure that only one greenthread can read any particular socket. Consider using a pools.Pool. If you do know what you're doing and want to disable this error, call eventlet.debug.hub_prevent_multiple_readers(False) - MY THREAD=; THAT THREAD=FdListener('read', 15, , )
    ```

    To resolve this error, specify the deployment order of the components in your blueprint, and provision the environment again. See step [9](blueprint_deploy_env.md#deployment_order) of [Deploying components with blueprints](blueprint_deploy_env.md#).


For more troubleshooting information, see the UrbanCode community on IBM® developerWorks®: [https://developer.ibm.com/answers/?community=urbancode](https://developer.ibm.com/answers/?community=urbancode).

**Parent topic:** [Troubleshooting modeling and provisioning cloud environments](../../com.ibm.udeploy.doc/topics/trouble_blueprints_ov.md)

