# Installing and uninstalling test fixes \(patches\) from the server

Test fixes are provided by IBM® support to correct specific issues. They are applied to the server as patches.

Ensure that you have the correct version of the server installed, as listed in the readme file for the test fix.

In most cases, test fixes come with specific instructions. In general, these instructions look like the following steps. However, always use the instructions in the readme file or the instructions that are provided by IBM support.

1.   Stop the server. 
2.   Download the file or files for the test fix. 
3.   Copy the files from the archive file to the folder app\_data/patches folder, where appdata is the application data folder. The default application data folder is /opt/ibm-ucd/server/appdata on Linux™ and C:\\Program Files\\ibm-ucd\\server\\appdata on Windows™. 
4.   Start the server. 
5.   Log in to the server. 
6.   Click **Settings** \> **Patches** and verify that the test fix is installed. 

To uninstall the test fix, stop the server, remove the files from the patches folder, and restart the server.

**Parent topic:** [Installing HCL UrbanCode Deploy](../../com.udeploy.install.doc/topics/install_ch.md)

