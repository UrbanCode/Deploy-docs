# VMware vRealize Automation resource types

These Heat resource types represent elements on the cloud. To install these types into a Heat engine, see

To install these types into a Heat engine, see [Extending an existing OpenStack engine](../../com.udeploy.install.doc/topics/extending_an_engine_for_openstack.md).

-   **[IBM::VRA::Server](../../com.edt.heat.reference.doc/topics/ref_ibm_vra_server.md)**  
These Heat resource types represent elements on VMware vRealize Automation. These types are discovered from vRealize Automation and are the results of data collection from the defined reservations and endpoints. HCL® UrbanCode™ Deploy supports VMware vCenter integration for this release. The templates are represented in the palette.
-   **[IBM::VRA::NetworkInterface](../../com.edt.heat.reference.doc/topics/ref_ibm_vra_networkinterface.md)**  
This resource represents a network interface on a VMware vRealize Automation image. It points to its software component type that is already defined in VMware vRealize Automation. You can set variables to the script type by using the input properties that follow. This new type for vRealize Automation is not overridden in the configuration file.
-   **[IBM::VRA::SoftwareComponent](../../com.edt.heat.reference.doc/topics/ref_ibm_vra_component.md)**  
This resource represents a discovered component. It points to its software component type that is already defined in VMware vRealize Automation. You can set variables to the script type by using the input properties that follow. This new type for vRealize Automation is not overridden in the configuration file.
-   **[IBM::VRA::Deployment](../../com.edt.heat.reference.doc/topics/ref_ibm_vra_deployment.md)**  
Set deployment timeout properties, service, and entitlement names. Deployment is a new type for VMware vRealize Automation; properties are not overridden in the configuration file.

**Parent topic:** [Heat resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_ov.md)

