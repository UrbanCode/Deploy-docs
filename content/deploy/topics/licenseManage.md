# License management {#licenseManage .concept}

IBM® UrbanCode® Deploy provides a 60-day license-free evaluation period. To use all product features after the evaluation period, you must have a license.

Unless you provide the location of a license server when you install IBM UrbanCode Deploy, a 60-day evaluation period begins when you install the product. During evaluation, you can use all product features. A message on the web-based UI displays the number of days that remain in the evaluation period.

After the evaluation period, you can access IBM UrbanCode Deploy to view and edit items but you cannot run deployments. You can apply a license at any time.

For more information about setting up a Rational® Common Licensing server and applying licenses, see the Rational Common Licensing help: [Rational Common Licensing v8.1.4 - 8.1.4.9 documentation](http://www-01.ibm.com/support/knowledgecenter/SSSTWP_8.1.4/com.ibm.rational.license.doc/helpindex_RCL.html)

The [Rational License Key Center](https://licensing.subscribenet.com/control/ibmr/login) is an online licensing tool. You can use this tool to generate or return your IBM Rational product license keys.

The IBM UrbanCode Deploy server is supported on z/Linux. While the licensing component is not supported on z/Linux, IBM UrbanCode Deploy tracks agent usage, called agent high-water marks. You can use these records to estimate license use on you z/Linux installation. See [Tracking agent usage](license_agentTracking.md).

**Note:** To minimize interruptions in access to your license server, you can configure it for high availability. See [High-availability options for Rational License Key Server](http://www-01.ibm.com/support/docview.wss?uid=swg27036356).

-   **[License scenarios](../../com.ibm.udeploy.install.doc/topics/license_scenarios.md)**  
After the evaluation period, you must acquire a license before you can use all product features. Several different license scenarios are available. Depending on the scenario, you might need to apply licenses to IBM UrbanCode Deploy servers, agents, or both.
-   **[Mixed mode licensing](../topics/mixed_mode_licensing.md)**  
Mixed Mode Licensing gives you the ability to use both Authorized Agent licenses and Floating licenses on the same UrbanCode instance for greater flexibility.
-   **[Applying licenses to servers and agents](../../com.ibm.udeploy.install.doc/topics/license_apply.md)**  
To use licenses, you install a Rational Common Licensing server, import your license keys, and link the IBM UrbanCode Deploy servers or agents to the license server.
-   **[Tracking agent usage](../topics/license_agentTracking.md)**  
You can track daily agent usage. Agent usage can provide a rough estimate of agent license use.

**Parent topic:** [Configuring](../topics/c_node_configuring.md)

