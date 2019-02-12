# Connecting to Amazon Web Services

To connect to Amazon Web Services \(AWS\), you must provide AWS account information in a functional ID. You must also register Amazon Elastic Compute Cloud \(EC2\) images with the cloud discovery service.

The following diagram shows a typical topology for this scenario. The blueprint design server and engine connect to Amazon Web Services. For authentication information, the blueprint design server connects to the Keystone identity service and optionally to an LDAP server.![A topology that includes the blueprint design server, an engine, Amazon Web Services, a Keystone server, and an optional LDAP server](../images/cloud_connect_amazon_a.gif)



-   **[Connecting the blueprint design server to Amazon Web Services](../../com.edt.doc/topics/cloud_connect_amazon_server.md)**  
To connect the blueprint design server to Amazon Web Services \(AWS\), map the AWS account information to a functional ID. Then, assign that functional ID to a team.
-   **[Registering Amazon EC2 images with the cloud discovery service](../../com.edt.doc/topics/integrate_ec2_image.md)**  
To use the blueprint designer to model environments on Amazon Web Services, you must register Amazon Elastic Compute Cloud \(EC2\) images with the cloud discovery service.

**Parent topic:** [Connecting to clouds through the blueprint designer](../../com.edt.doc/topics/security_cloud_connection.md)

