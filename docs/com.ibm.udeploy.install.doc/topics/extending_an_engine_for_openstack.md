# Extending an existing OpenStack engine

To connect the blueprint design server to an OpenStack-based cloud, extend the Heat orchestration engine that is associated with the cloud. By extending the engine, you add custom types to it so that you can use it with the blueprint design server.

-   You must have an OpenStack Heat orchestration engine that is connected to a Keystone service. The engine must be at the Icehouse, Juno, Kilo, Liberty, Mitaka, or Newton level. The engine and Keystone service are required regardless of the type of cloud that you use. If you do not have an engine, you can install one that includes the custom types and is connected to a Keystone service. See [Installing the engine](install_engine.md). If your OpenStack Heat orchestration engine is not connected to a Keystone service, you must connect to it to a Keystone service. See [Connecting engines to Keystone servers](install_engine_new_keystone.md#)..
-   The upgrade-standalone-ucd-heat-engine.sh script can only be used with the provided heat engine that comes with HCL UrbanCode Deploy blueprint designer. It installs both the HCL UrbanCode Deploy plug-in and the ibm-cloud-ext package
-   In the case that you are using OpenStack Newton or higher, you must diable the Heat convergence mode before installing the plugins. Open the heat.conf file \(/etc/heat/heat.conf\), and set convergence\_engine to False. Then, restart the Heat engine services by running the systemctl stop and start commands.

Before you install the engine, ensure that you do the following steps:

1.  Root access is required for installation.
2.  The operating system must be configured with required packages and dependencies before you install the engine. The system might need network access to install these packages. Make sure that the system is connected to a package manager, such as a Yum server.
3.  Enable the optional "rhel-7-server-optional-rpms" repository.
    -   On RHEL systems that use the Red Hat Network subscription-based package manager, use the following command:

        ```
        subscription-manager repos --enable=rhel-7-server-optional-rpms
        ```

    -   On virtual machines that are hosted on Amazon Web Services, run the following command:

        ```
        yum-config-manager --enable rhui-REGION-rhel-server-optional
        ```

4.  Determine whether the `akonadi` package is installed on the system.

    ```
    rpm -ql akonadi
    ```

5.  If the `akonadi` package is installed, remove it:

    ```
    yum remove -y akonadi
    ```

6.  Determine whether the program `qpid` is installed on the system.
    -   On RHEL version 7, run the following command:

        ```
        systemctl status qpidd.service
        ```

7.  If the program `qpid` is running on the system, stop its service.
    -   On RHEL version 7, run the following command:

        ```
        systemctl stop qpidd.service
        ```


To deploy environments to OpenStack clouds and clouds that are based on OpenStack, you install the blueprint design server and extend the Heat engine that is associated to the cloud. In this case, you do not use the Heat engine that comes with HCL UrbanCode Deploy.

To extend a Heat orchestration engines for the blueprint design server, do the following steps:

1.   Download and extract the installation files for the engine. These files are available for download from the IBM® Passport Advantage® website. See the [IBM UrbanCode Deploy download document](https://www.ibm.com/software/passportadvantage/pao_customer.html). 
2.   Change to the ibm-ucd-patterns-install/engine-install/ directory. 
3.   From the command line, run the ./extend-ucd-existing-engine.sh command to install the HCL UrbanCode Deploy plug-in. 
4.   The installer asks if you have satisfied the dependencies. If you configured the system with the prerequisites for the engine, press `Y`. 
5.   Read the license agreements for the software package. Press Space to show one page at a time, or press `F` to show the entire license. 
6.   If you agree to the terms of all of the license agreements, press `Y`, and then press Enter. 
7.   If you use a Kilo-level Heat engine and apply Chef roles to environments, modify the engine to be compatible with Chef. Run the following commands:

    ```
    sed -i '125,127 s/^/#/' /usr/lib/python2.7/site-packages/heat/engine/resources/openstack/heat/software_deployment.py
    sed -n '125,127p' /usr/lib/python2.7/site-packages/heat/engine/resources/openstack/heat/software_deployment.py
    ```

    The following text is displayed in the command line:

    ```
    # constraints=[#
        constraints.CustomConstraint('nova.server')# ]
    ```

8.   Restart the engine and the Heat API. See the documentation for your cloud system.
9.   Verify that the new resource types are available in the engine by running the following command: 

    ```
    heat resource-type-list
    ```

    If you see resource types that start with `IBM::UrbanCode`, such as `IBM::UrbanCode::SoftwareDeploy::UCD`, you correctly added the required types to the engine.


The engine is configured to work with the blueprint design server.

Install a blueprint design server.

