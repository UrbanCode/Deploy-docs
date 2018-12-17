# Troubleshooting cloud connections

To troubleshoot a cloud connection, make sure that the information for the cloud is correct and that the components of the blueprint design server can access the cloud.

-   **Check the logs**

    The default location for the blueprint design server logs is /opt/ibm-ucd-patterns/logs. The default location for the engine logs is /var/log/heat/.

-   **Confirm software components**

    Ensure that you have installed all the necessary components. Regardless of which type of cloud you are connecting to, the connection requires an OpenStack Keystone server, an engine, and a blueprint design server. See [Connecting to clouds through the blueprint designer](security_cloud_connection.md).

-   **Confirm connection information**

    The connection information for the cloud must match the information on other systems. For example, the URL of the OpenStack identity service \(Keystone\) must be exactly the same \(including any trailing slashes\) in the authentication realm and on the allowed\_auth\_uris parameter of the engine configuration file.

-   **Provide proxy connection information**

    If you provision to Amazon Web Services and use a proxy server, you must provide the proxy server URL and port. Both the system that hosts the engine and the system that hosts the cloud discovery service require this proxy.

    -   For a Linux™ operating system, create a file that is named .boto in the /home/user\_name directory.
    -   For a Windows™ operating system, create a file that is named boto.config in the C:\\Users\\user\_name directory. Then, set a user environment variable that is named BOTO\_CONFIG to the full path of the file, `C:\Users\user\_name\boto.config.`
    In the file that you created, add the following lines:

    ```
    [Boto]
    proxy=proxy\_host\_name
    proxy_port=proxy\_port\_number
    ```

    See [Boto Config](http://boto.readthedocs.org/en/latest/boto_config_tut.html).

    After you modify the boto.config file, you must restart the cloud discovery service. To restart the cloud discovery service, see [Stopping the blueprint designer, cloud discovery service, and engine](../../com.ibm.udeploy.install.doc/topics/stop_patterns.md) and [Stopping the blueprint designer, cloud discovery service, and engine](../../com.ibm.udeploy.install.doc/topics/stop_patterns.md).

-   **Confirm the blueprint design server system time**

    If you provision to Amazon Web Services and see a `Connection Failed` error in the blueprint designer, confirm that the system time of the blueprint design server is correct.


For more troubleshooting information, see the UrbanCode community on IBM® developerWorks®: [https://developer.ibm.com/answers/?community=urbancode](https://developer.ibm.com/answers/?community=urbancode).

**Parent topic:** [Troubleshooting modeling and provisioning cloud environments](../../com.ibm.udeploy.doc/topics/trouble_blueprints_ov.md)

