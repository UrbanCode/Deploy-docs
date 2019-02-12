# Modeling environments with referenced resources

Rather than adding specific resources to a blueprint, you can add referenced resources. Referenced resources include images, networks, routers, storage volumes, security groups, and components. Referenced resources are generic when you create the blueprint. You can then specify the exact resource to use at provisioning time. By using referenced resources, you can create one blueprint that you can provision on multiple clouds. For example, you can create a blueprint that you can provision for a development environment and for a testing environment, and use different resources in the two environments.

-   Connect the blueprint design server to a cloud system. See [Connecting to clouds through the blueprint designer](security_cloud_connection.md).
-   Make sure that your user account is authenticated to a cloud system. See [Setting up access to clouds in the blueprint designer](../../com.udeploy.admin.doc/topics/security_auth_bds.md).
-   Connect the blueprint design server to the server. See [Connecting the blueprint design server to the server](../../com.udeploy.doc/topics/ucdp_integrate.md).
-   Log in to the blueprint designer.
-   At the top of the page, select the cloud project and region to use.

1.   In the blueprint designer, on the **Diagram** tab, create a blueprint. For information on creating and editing blueprints, see [Creating files with the blueprint designer](blueprint_edit.md#).
2.   Add a referenced resource to the blueprint. For example, add a Referenced Network resource to the blueprint. The Reference Parameter window is displayed.
3.   Specify values for **Key**, **Label**, and **Description** for the resource, or accept the defaults. The **Key** value is used to identify the resource in the source code of the blueprint. The **Label** value is used to identify the resource in the blueprint diagram. The **Description** text is available when you provision the blueprint. The referenced resource is added to the blueprint diagram, and the corresponding parameters and parameter groups are added to the blueprint source code.
4.   Continue adding resources to complete the blueprint. When you add a Referenced Security Group or Referenced Storage Volume resource to a blueprint, you can reuse any existing references of those types by selecting them from the **Reuse Existing Reference** list on the Reference Parameter window. You can create a blueprint that contains only referenced resources.
5.   To adjust a parameter or parameter group, click the **Edit Parameters** icon at the top of the graphical editor. The Parameters window is displayed, listing all parameters in the blueprint. You can edit and delete parameters and parameter groups in the Parameters window.
6.   To place constraints on a parameter, edit the parameter as described in the previous step and then select a constraint from the **Constraint** list. For example, if you select the **Allowed Pattern** constraint, you can then specify a regular expression or select a pre-defined **Pattern** value, and specify **Error Message** text to display if the parameter does not match the pattern. The source code for the referenced resource now includes a constraints value. In the Parameters window, constrained parameters are indicated by \(P\).

When you provision a blueprint that contains referenced resources, the parameters in the blueprint are separated into parameter groups and identified with the labels that you specified. Click a parameter group name to open that group, and then select values for each parameter.

Typically, you create a configuration file for each environment where you provision the blueprint, as described in the [Provisioning environments from the blueprint designer \(through OpenStack Heat\)](env_provision_edt.md#) topic.

**Parent topic:** [Blueprint properties, attributes, and parameters](../../com.udeploy.doc/topics/blueprint_props_ov.md)

