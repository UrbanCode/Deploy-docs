# Creating statuses

Define component version and inventory statuses on the **Statuses** tab.

1.  Click **Settings** \> **Statuses**.
2.  For the status type to create, click **Add Status**. 
3.  Configure the status in the Add Status window: 

    |Parameter|Description|
    |---------|-----------|
    |**Name**|Identifies the status and is included in many UI elements.|
    |**Description**|Conveys more information about the process.|
    |**Color**|Defines the status color that is displayed in the UI.|
    |**Unique**|When checked, specifies that only a single instance of the status describes a component. For inventory or snapshot statuses, an application removes the status from existing versions in the environment or resource inventory. For version statuses, the status can be used by only one version at a time.|
    |**Required Role**|Specifies the user role that is necessary for a user to assign the status.|

4.  Save your work when finished.Statuses are stored in the HCL® UrbanCode™ Deploy database.

    **Tip:** Default statuses are defined in an XML file, which you can freely edit to add your own values.


**Parent topic:** [Managing security](../../com.udeploy.admin.doc/topics/security_ch.md)

