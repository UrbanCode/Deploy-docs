# Importing cost information from clouds

You can import cost information from clouds to populate cost centers. Importing cost information in this way retrieves information about the prices of cloud resources.

**Warning:** Importing cost information from clouds is deprecated. Imported cost data from clouds is provided as-is and is not guaranteed to be accurate. After you import cost information, verify it with the cloud manually.

-   Connect to a cloud. See [Connecting to clouds through the blueprint designer](security_cloud_connection.md).
-   Importing cost information from clouds on the internet, such as Amazon Web Services and SoftLayer®, requires access to the internet.

1.   In the blueprint designer, as an administrator, click **Settings** \> **Cost Centers**. 
2.  Click **Add Cost Center**. 
3.  Specify a name for the cost center.You can name the cost center after the cloud that it applies to. If multiple clouds use the same cost structure, you can give the cost center a generic name that applies to the multiple clouds.
4.  In the **Source** list, select **Cloud**.
5.  Click **Save**.
6.  For the cost center, go to the **Edit** tab. 
7.  Click **Import Cost Data**.
8.  If you agree to the terms and conditions, select the **I agree to the terms and conditions** check box.
9.   In the **Cloud** list, select the cloud connection and then click **Import**. The blueprint design server accesses the cloud and attempts to download cost information. The blueprint design server retrieves the factors that affect environment cost, such as flavors, volumes and regions. This information appears on the **Cost Factors** tab. In some cases the cloud also provides prices, which appear on the **Cost Metrics** tab.
10. Go to the **Cost Factors** tab. This tab shows the factors that can be priced, such as the type of instance and the region on which the instance runs.
11. Verify the information on the **Flavor**, **Instance Type**, **Region**, and **Volume** tabs by comparing with the cloud manually and making updates as necessary. 

    **Note:** The **Instance Types** tab always shows a default set of instance types.

12. Update or remove the default set of instance types to match the instance types on the cloud.
13.  On the **Cost Metrics** tab, verify and update the costs of the different instances, volumes, and IP addresses on the cloud. For more information, see [Specifying costs for cloud resources manually](cost_center_clouds.md). Cost data is added automatically for Amazon Web Services, but in all cases you must verify the cost information manually.

When you provision an environment from the blueprint designer, as described in [Provisioning environments from the blueprint designer \(through OpenStack Heat\)](env_provision_edt.md), the blueprint design server estimates the cost per hour of the environment.

**Note:** You cannot estimate the cost for cloud environments that you provisioned by using a composite blueprint.

**Parent topic:** [Estimating the cost for cloud environments](../../com.edt.doc/topics/cost_ov.md)

**Parent topic:** [Estimating the cost for cloud environments](../../com.udeploy.doc/topics/cost_ov.md)

