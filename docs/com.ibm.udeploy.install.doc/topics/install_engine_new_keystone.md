# Connecting engines to Keystone servers

If you have an engine that is configured to work with the blueprint design server, you can connect it to a Keystone server for a new cloud.

-   You must have an engine that is configured to work with the blueprint design server. See [Installing the engine](install_engine.md#).
-   You must have an OpenStack Keystone server.

These steps configure an engine to accept connections to a new cloud. They do not create a connection from the blueprint designer to that cloud; to create this connection, see [Connecting to clouds through the blueprint designer](../../com.ibm.edt.doc/topics/security_cloud_connection.md).

1.  On the engine, open Heat configuration file.By default, this file is in the location /etc/heat/heat.conf .
2.   In this file, find the allowed\_auth\_uris property in both the auth\_password and, if applicable, the ec2authtoken sections. This property is a comma-separated list of Keystone servers that the engine can contact.
3.   Add the complete URL to the Keystone server to each allowed\_auth\_uris property. For example, if the engine connects to clouds at `cloud1.example.com` and `cloud2.example.com`, the property might look like the following example:

    ```
    allowed_auth_uris=http://cloud1.example.com:5000/v2.0,http://cloud2.example.com:5002/v2
    ```

4.  Save and close the file.
5.   Restart the engine: In version 6.2.1.1 or later, run the following command:

    ```
    systemctl restart openstack-heat-engine.service
    ```

    In versions before 6.2.1.1, run the following command:

    ```
    service openstack-heat-engine restart
    ```

6.   Restart the Heat API: In version 6.2.1.1 or later, run the following command:

    ```
    systemctl start openstack-heat-api.service
    ```

    In versions before 6.2.1.1, run the following command:

    ```
    service openstack-heat-api restart
    ```


**Parent topic:** [Overview of integrations](../../com.ibm.udeploy.doc/topics/integrat_ov.md)

