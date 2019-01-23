# Configuring services and entitlements in VMware vRealize Automation

After you configure the integration with VMware vRealize Automation Enterprise, you can create a default service and a default entitlement to use with the blueprint designer.

You can create a default service and a default entitlement in VMware vRealize Automation Enterprise for the blueprint designer to use. If you create a new service and entitlement for the blueprint designer, you do not need to specify these values in blueprints that you create in the blueprint designer. If you do not create the IBM UrbanCode Provision Service service and IBM UrbanCode Entitlement entitlement, as described below, you must specify the service and entitlement to use in each blueprint that you create. See [Modeling environments for VMware vRealize Automation](blueprint_edit_vra.md#).

1.  With an account that has tenant administrator or catalog administrator privileges, complete the following steps:
2.   Log in to vRealize Automation as user that is assigned one of these roles: 
    -   Tenant administrator
    -   Business group manager
    -   Catalog administrator
3.   Create the IBM UrbanCode Provision Service service: 
    1.   Click the **Administration** tab, and then click **Catalog Management** \> **Services**. 
    2.   Click **New**, and in the **Name** field, enter IBM UrbanCode Provision Service. 

        **Note:** You must set IBM UrbanCode Provision Service as the service name.

    3.   Set the service status to **Active**. 
    4.   Complete the other fields as applicable. 
    5.   Click **OK**. 
4.   Create the IBM UrbanCode Entitlement entitlement: 

    1.   Click the **Administration** tab, and then click **Catalog Management** \> **Entitlements**. 
    2.   Click **New**, open the **General** tab, and then complete these fields: 
        -   **Name**

            **Note:** You must set IBM UrbanCode Entitlement as the entitlement name.

        -   **Users & Groups**
        -   **Business Group**
    3.   To open the **Items & Approvals** tab click **Next**, and then click the plus sign \(+\) icons to add entitled services, entitled items, and entitled actions. 
    4.   Click **Finish**. 
    **Tip:** To change an existing service, follow the previous steps and remove the added settings.


**Parent topic:** [Connecting to VMware vRealize Automation v7 and v7.1](../../com.ibm.edt.doc/topics/cloud_connect_vra.md)

