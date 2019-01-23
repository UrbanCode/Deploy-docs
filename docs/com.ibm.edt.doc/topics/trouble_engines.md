# Troubleshooting engines

If you are having trouble with an engine, here are some things that might help.

-   **Check the logs**

    The default location for the engine logs is /var/log/heat/.

-   **Restart the engine**

    In version 6.2.1.1 and later, to restart the engine and the related Heat API service, run the following commands:

    ```
    systemctl restart openstack-heat-engine.service
    ```

    ```
    systemctl restart openstack-heat-api.service
    ```

    In versions before 6.2.1.1, to restart the engine and the related Heat API service, run the following commands:

    ```
    service openstack-heat-engine restart
    ```

    ```
    service openstack-heat-api restart
    ```

-   **Verify the resource types**

    Verify that the engine has the resource types that are used by the blueprint design server by running the following command:

    ```
    heat resource-type-list
    ```

    If you see resource types that start with `IBM::EC2` and `IBM::UrbanCode`, such as `IBM::EC2::Port` and `IBM::UrbanCode::SoftwareDeploy::UCD`, the engine has the correct resource types. If not, see [Extending an existing OpenStack engine](../../com.ibm.udeploy.install.doc/topics/extending_an_engine_for_openstack.md).

-   **Verify the allowed URLs for connections**

    Verify that the engine is allowed to access the Keystone server. Ensure that ports are open and network connectivity is available. Also, verify that the Keystone server is listed in the allowed\_auth\_uris parameter of the engine configuration file; see [Connecting engines to Keystone servers](../../com.ibm.udeploy.install.doc/topics/install_engine_new_keystone.md).

-   **Modify the communications rate between images and the Heat engine**

    If you provision images that use Chef roles, your Heat engine might experience excessive load from those virtual machines or generate excessive API calls. If you provision images to SoftLayer, the environment table in the blueprint designer might display a stack failure error about exceeding the API request limit that resembles this message: `“error": "Rate limit of 50 requests for every 1 second(s) exceeded.”` You can reduce the communication frequency between your virtual machines and the engine.

    On each image that contains a Chef role, create a script that sets the polling\_interval to the Heat engine. This value is the frequency in seconds with which the image communicates with the Heat engine. In the following code, the polling\_interval value is `90` seconds:

    ```
    #!/bin/bash
    grep -q '^polling_interval' /etc/os-collect-config.conf
    if [ $? -eq 1 ]; then
    sed -i '2ipolling_interval = **90**' /etc/os-collect-config.conf
    else
    sed -i "s|^polling_interval =.*|polling_interval = **90**|g" /etc/os-collect-config.conf
    fi
    kill -9 $(ps -ef | grep os-collect-config | grep -v grep | awk {'print $2'})
    nohup /usr/bin/os-collect-config &
    exit 0
    ```

    Ensure that the polling\_interval value is short enough that the virtual machine can collect any changes from the Heat engine before the stack timeout elapses. The default timeout value is 60 minutes, but you can set the timeout value for each cloud. See [Creating cloud projects for the blueprint designer](../../com.ibm.udeploy.admin.doc/topics/security_projects.md#).

    Run the script on each image.

-   **Verify admin access to the heat stack domain**

    If you extended a Kilo heat engine and do not have admin permissions for your OpenStack-based cloud, you must obtain admin access to the heat domain of your heat engine before you provision an autoscaling group or deploy outside of HCL® UrbanCode™ Deploy. If you do not have admin access to the heat domain, when you provision an autoscaling group, the following error message is displayed:

    ```
    KS-D4A211B You are not authorized to perform the requested action: identity:list_roles (HTTP 403)
    ```

    From your engine administrator, obtain the following parameters and values for your OpenStack-based cloud:

    ```
    stack_user_domain_name=heat
    stack_domain_admin=heat\_stack\_admin
    stack_domain_admin_password=heat\_stack\_admin\_password
    ```

    Locate each parameter in the engine heat.conf file, which is in the /etc/heat directory by default, and, if no value is provided, then enter the value that your engine administrator provided. You might need to uncomment the line of code that contains the parameter. If parameters are not present in the heat.conf file, then add the lines of code that contain them.

    If the engine administrator cannot provide information for that domain, the engine administrator must create the domain. For example, to create the domain for a Kilo version engine on a Red Hat Enterprise Linux version 7, Fedora version 21, or CentOS version 7 operating system, see [Install and configure Orchestration](http://docs.openstack.org/kilo/install-guide/install/yum/content/heat-install-controller-node.html). Note that the process is different for each version of OpenStack. For example, for the equivalent process for a Mitaka version engine, see [Install and configure](http://docs.openstack.org/mitaka/install-guide-rdo/heat-install.html)

    To connect to multiple OpenStack-based clouds by using admin access to the heat domain of an extended heat engine, you must use a separate engine for each OpenStack-based cloud.


For more troubleshooting information, see the UrbanCode community on IBM® developerWorks®: [https://developer.ibm.com/answers/?community=urbancode](https://developer.ibm.com/answers/?community=urbancode).

-   **[Engine troubleshooting script](../../com.ibm.edt.doc/topics/troubleshooting_script.md)**  
If you have a problem with the HCL UrbanCode Deploy engine, run the troubleshooting script to provide IBM Software Support and developers information about the status of your engine. Consider running this script and having the results available before you call IBM Software Support. This script applies to OpenStack Heat orchestration engines that are at the Juno or Kilo level.
-   **[Troubleshooting Heat-engine plug-in extensions](../../com.ibm.edt.doc/topics/r_t-shoot_heat_ext_plgin.md)**  
Installing the Blueprint Designer Heat extension plug-ins into an IBM Cloud Manager Heat engine results in stopping SSL communication.

**Parent topic:** [Troubleshooting modeling and provisioning cloud environments](../../com.ibm.udeploy.doc/topics/trouble_blueprints_ov.md)

