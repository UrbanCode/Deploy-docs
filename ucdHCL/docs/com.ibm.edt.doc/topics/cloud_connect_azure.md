# Connecting to Microsoft Azure

To connect to Microsoft™ Azure, you must provide Azure account information in a functional ID.

The following diagram shows a typical topology for this scenario. The blueprint design server and engine connect to Azure. For authentication information, the blueprint design server connects to the Keystone identity service and, optionally, to an LDAP server.![A topology that includes the blueprint design server, an engine, Azure, a Keystone server, and an optional LDAP server](../images/cloud_connect_azure_a.gif)



-   **[Connecting the blueprint design server to Azure](../../com.ibm.edt.doc/topics/cloud_connect_azure_server.md)**  
To connect the blueprint design server to Microsoft Azure, map the Azure account information to a functional ID. Then, assign that functional ID to a team.
-   **[Registering Azure marketplace images with the cloud discovery service](../../com.ibm.edt.doc/topics/integrate_azure_image.md)**  
To use Microsoft Azure marketplace images in the blueprint designer, you must register images with the cloud discovery service.
-   **[Registering Azure custom images with the cloud discovery service](../../com.ibm.edt.doc/topics/integrate_azure_private.md)**  
To use Microsoft Azure custom images in the blueprint designer, you must register the images with the cloud discovery service.

**Parent topic:** [Connecting to clouds through the blueprint designer](../../com.ibm.edt.doc/topics/security_cloud_connection.md)

