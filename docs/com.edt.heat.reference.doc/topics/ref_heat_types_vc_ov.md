# VMware vCenter resource types

These Heat resource types represent elements on VMware vCenter.

To install these types into a Heat engine, see [Extending an existing OpenStack engine](../../com.udeploy.install.doc/topics/extending_an_engine_for_openstack.md).

**Note:** VMware NSX is required for creating network resources on VMware clouds, and some resources require NSX. See [Modeling new network resources](../../com.edt.doc/topics/blueprint_network_create.md#).

-   **[IBM::VCenter::Network](../../com.edt.heat.reference.doc/topics/res_ibm_vc_network.md)**  
This resource type represents a network on VMware vCenter. You must use VMware NSX to access this resource type.
-   **[IBM::VCenter::Port](../../com.edt.heat.reference.doc/topics/res_ibm_vc_port.md)**  
This resource type represents a port on a VMware vCenter image. It extends the type OS::Neutron::Port.
-   **[IBM::VCenter::Router](../../com.edt.heat.reference.doc/topics/res_ibm_vc_router.md)**  
This resource type represents a router on VMware vCenter.
-   **[IBM::VCenter::RouterInterface](../../com.edt.heat.reference.doc/topics/res_ibm_vc_routerinterface.md)**  
This resource type represents a router interface on VMware vCenter. You must use VMware NSX to access this resource type.
-   **[IBM::VCenter::SecurityGroup](../../com.edt.heat.reference.doc/topics/res_ibm_vc_securitygroup.md)**  
This resource type represents a security group on VMware vCenter. It extends the type OS::Neutron::SecurityGroup. You must use VMware NSX to access this resource type.
-   **[IBM::VCenter::Server](../../com.edt.heat.reference.doc/topics/res_ibm_vc_server.md)**  
This resource type represents a server on VMware vCenter. It extends the type OS::Nova::Server.
-   **[IBM::VCenter::Volume](../../com.edt.heat.reference.doc/topics/res_ibm_vc_volume.md)**  
This resource type represents a volume on VMware vCenter. It extends the type OS::Cinder::Volume.
-   **[IBM::VCenter::VolumeAttachment](../../com.edt.heat.reference.doc/topics/res_ibm_vc_volumeAttachment.md)**  
This resource type represents a volume attachment on VMware vCenter. It extends the type OS::Cinder::VolumeAttachment.

**Parent topic:** [Heat resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_ov.md)

