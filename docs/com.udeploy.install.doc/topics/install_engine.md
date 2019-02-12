# Installing the engine

To connect the blueprint design server to a cloud system, you need a Heat orchestration engine. Heat orchestration engines interpret blueprints and use them as patterns for cloud resources. To connect to OpenStack-based clouds, you extend the engine that is associated with the cloud. To connect to all other clouds, you install an engine with HCL® UrbanCode™ Deploy.

-   See the system requirements in [System requirements and performance considerations](sysRequire.md).
-   In the case that you are using Openstack Newton or higher, you must disable Heat convergence mode before installing the plugins. Open the `heat.conf` file \(/etc/heat/heat.conf\), and set `convergence_engine` to `False`. Then, restart the Heat engine services by running the `systemctl` stop and start commands.

The blueprint designer uses OpenStack Heat engines that are customized with special resource types, which represent artifacts on HCL UrbanCode Deploy and on cloud systems. With these resource types, you can create blueprints that include HCL UrbanCode Deploy components and blueprints that you can provision to clouds.

You can connect to non-OpenStack clouds by installing an engine provided by HCL UrbanCode Deploy, or you can connect to an OpenStack cloud by extending the Heat engine that is associated with the OpenStack cloud. For information that shows the typical topologies, see [Systems and topology overview](../../com.udeploy.doc/topics/ov_systems.md).

**Connecting to a non-OpenStack cloud:**

To connect to a non-OpenStack cloud, you must install a standalone engine provided by HCL UrbanCode Deploy.

-   [Installing a standalone engine](install_engine_standalone.md): To deploy environments to non-OpenStack clouds, such as Amazon Web Services, SoftLayer, VMware, Google Cloud, and Microsoft Azure, you install the blueprint design server and Heat engine through IBM UrbanCode Deploy. You can install the engine in interactive mode or in silent mode.

In this scenario, you install by using the `install.sh` script. This script installs an OpenStack Keystone and Heat engine provided by the HCL UrbanCode Deploy blueprint designer. The Heat engine is installed with plugins that allow the blueprint designer to integrate with an HCL UrbanCode Deploy server and with non-OpenStack clouds.

**Connecting to an OpenStack-based cloud:**

To connect to an OpenStack-based cloud, you must extend the Heat engine that is associated with the OpenStack cloud; do not use an engine that is provided by HCL UrbanCode Deploy.

-   [Extending an existing OpenStack engine](extending_an_engine_for_openstack.md): To connect the blueprint design server to an OpenStack-based cloud, extend the Heat orchestration engine that is associated with the cloud. By extending the engine, you add custom types to it so that you can use it with the blueprint design server.

In this scenario, you install the plugins by using the `extend-ucd-existing-engine.sh` script. This script installs the plugin into an already existing Heat engine of your OpenStack installation. This plugin allows the blueprint designer to integrate with an HCL UrbanCode Deploy server.

**Related topics**:

