# Installing plug-ins

Plug-ins can be installed at any time. You do not need to restart the server after you install a plug-in.

You can upgrade a plug-in by installing the new version over the old version.

1.   Download the installation files for one or more plug-ins from the following site: [https://developer.ibm.com/urbancode/plugins/ibm-urbancode-deploy/](https://developer.ibm.com/urbancode/plugins/ibm-urbancode-deploy/) 

    Documentation for plug-ins and the steps in the plug-ins is available on that site.

2.  Load the plug-ins: 
    1.  For automation plug-ins, click **Settings** \> **Automation Plugins** and click **Load Plugin**.
    2.  For source plug-ins, click **Settings** \> **Source Config Plugins** and click **Load Plugin**.
    3.  Enter the path to the compressed plug-in file, and then click **Submit**.

The plug-in is listed on either the Automation Plugins pane or the Source Config Plugins pane. After the plug-in is installed, it is available immediately.

**Note:** You cannot roll back a plug-in version to a previous version. To move to a previous version of a plug-in, follow these steps:

1.  Uninstall the later version of the plug-in. Now, in all processes, steps from that plug-in are shown with the text "PLUGIN DELETED." The processes cannot run until you install a new version of the plug-in and recreate the steps.

    **Note:** If the plug-in is used in one or more snapshots, the server retains the pertinent steps to avoid breaking the snapshots. However, you cannot add these steps to new processes after you delete the plug-in.

2.  Install the earlier version of the plug-in.
3.  In each process that used steps from that plug-in, recreate the steps and delete the steps that are labeled "PLUGIN DELETED." The process steps do not work until you recreate them, even if you have installed a new version of the plug-in.

**Parent topic:** [Installing HCL UrbanCode Deploy](../../com.udeploy.install.doc/topics/install_ch.md)

**Parent topic:** [Managing security](../../com.udeploy.admin.doc/topics/security_ch.md)

