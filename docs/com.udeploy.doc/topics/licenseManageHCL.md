# HCL License management

Once you purchase HCL UrbanCode® Deploy you will receive notification of access to the HCL License Portal via email. You can manage your licenses associated with your order and download the software for installation.

You can access the HCL License Portal here:[https://hclsoftware.flexnetoperations.com/flexnet/operationsportal/logon.do](https://apac01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fhclsoftware.flexnetoperations.com%2Fflexnet%2Foperationsportal%2Flogon.do&data=02%7C01%7Cjoseph.londa%40hcl.com%7C935637ec570340770e9208d58ac7d029%7C189de737c93a4f5a8b686f4ca9941912%7C0%7C0%7C636567513180634748&sdata=6X7x3pX257s0rshf%2F%2BOhH9xHLTFWnlEUNRTpJpgwKzY%3D&reserved=0) 

The license portal provides both software distribution and management of your software entitlements purchased from HCL Products and Platforms. The portal provides you with control and flexibility on how to consume your licenses. Typically, an organization will have someone identified as a License Manager that has familiarity with the language of licenses, and you may wish to add them as a user. If not, you will find these instructions sufficient to begin using your HCL Software.

Add Users

Login to the portal using your email address and your reset password.

Use the navigation banner and click on **Accounts & Users** and then **List Users**.

Your account will be listed. Click on **Actions** and **Create**. Complete the web form required fields and any additional fields to the extent your organization requires. Link the new user to your account with the appropriate permissions

Create Devices

On the navigator bar hover on **Devices** and then click on **Devices**. Your list might be empty if this is your first purchase from HCL Products and Platforms, or you might see a list of devices that were previously created for your account. You may optionally use one of these previously created devices or create a new device for your recently purchased entitlements. Click on **Create Device** for creating a new device and you will come to the **New Device** window.

Enter a name for your device and check the **Runs License Server** box.

For server deployment select **Local** or **Cloud**. Your entitlement includes a download package to install the HCL Common Local License Server. It requires you to have a CA signed SSL certificate for your organization, and that will allow the Server to prove its identity to the connected applications.

Enter a Site Name that suits your organization

You will get a response screen that confirms the server was created. Record the License Server ID, as this will be used during the install of your purchased software to talk with the Local or Cloud License Server.

Set Admin Password

Now set the admin password for the server. Some HCL Products use the REST API to monitor your Cloud License Server which requires a password.

Hover on **Actions** and then click on **Set Password**.

Map Entitlements

Your entitlements must be mapped to either a preexisting Cloud License Server or the server you just created. Hover on **Actions** and then click on **Map Entitlements** .

You can map all of the entitlement to this server or split the entitlements between servers to allocate your purchase to different teams in the organization. You will be presented with a confirmation screen.

Download Package and Install

To obtain your entitled software for installing, hover on **Downloads** and then click on **List Downloads**.

Click on the UrbanCode license file . The latest version of the software and previous versions will be available to you. In addition, the HCL Common Local License will also be available for installing.

Select the file you want to download and click on **Download Selected Files**. Complete the download and use the Server ID during the install process to enable the product to talk with the local/cloud license server and consume the license quantity you allocated to that server.

The software will be authorized to use up to the allocation of entitlement you made on the server. You will be presented with a message if the entitlement has been consumed.

Clients that selected “Opt In” for Overdraft capability at the time of executing the Order Schedule will be able to exceed the entitlement level on demand for products that are transactional and will be billed on a monthly basis, or as defined in the terms, for the Overdraft Usage. The Terms of this practice are described on the Order Schedule in the Product Specific Terms. If you desire to have this capability enabled, contact the HCL Support organization. [https://www.hcltech.com/products-and-platforms/contact-support](https://www.hcltech.com/products-and-platforms/contact-support)

Run Reports

In the navigation bar, hover on **Usage** and then click on **Usage Report**. Select your account and then click on **Search**.

You can specify a **Product Line**Product Line and **As of Date** to narrow the report. A variety of report formats are also available and the data may be downloaded for your local use.

The data may also be viewed in a spreadsheet.

**Parent topic:** [Configuring](../topics/c_node_configuring.md)

