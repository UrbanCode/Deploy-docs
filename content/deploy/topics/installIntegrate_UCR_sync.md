# Installing IBM BluemixIBM DevOps Connect {#installIntegrate_UCR_sync .task}

Install IBM® Bluemix®IBM DevOps Connect to share data between IBM UrbanCode® Deploy, IBM UrbanCode Release, and IBM UrbanCode Cloud services and Bluemix Services.

To register DevOps Connect, you must have an IBMid. If you do not have an IBMid, see [https://www.ibm.com/account/profile/us?page=reg](https://www.ibm.com/account/profile/us?page=reg).

You must install a Java™ Runtime Environment version 7 or later on the host system and set the system `PATH` variable to its location.

DevOps Connect is compatible with all versions of IBM UrbanCode Release and versions 6.2.1.2 and later of IBM UrbanCode Deploy. A patch is available for earlier versions of IBM UrbanCode Deploy. You can download the patch from IBM developerWorks. To install the patch, follow these steps:

1.  Stop the IBM UrbanCode Deploy server.
2.  Place the patch files in the \\UCD\_server\\appdata\\patches. If you renamed the appdata folder during installation, use that folder instead.
3.  Restart the IBM UrbanCode Deploy server.

After you install a patch, DevOps Connect is compatible with IBM UrbanCode Deploy versions 6.2.0, 6.2.0.1, 6.2.0.2, 6.2.1, and 6.2.1.1. DevOps Connect is not compatible with IBM UrbanCode Deploy versions earlier than 6.2.0.

The DevOps Connect installation file is an executable JAR file. After you download the file, place it on a computer that has access to the products that you want to integrate with, such as IBM UrbanCode Deploy. You start DevOps Connect by running the JAR file.

After DevOps Connect starts, you can use a web browser to access the application's dashboard. The first time that you run DevOps Connect, you use your IBMid to register it with the IBM Cloud services. The IBM Cloud service issues an authentication token that is stored in the sync.properties file. On Windows, the sync.properties file and log files are stored in the \\Users\\my\_directory\\.ibm\\cloud-sync folder on the computer that hosts DevOps Connect. On Linux, the sync.properties file is stored in the /home/my\_directory/.ibm/cloud-sync folder.

**Note:** The /cloud-sync folder is created the first time that you run DevOps Connect.

By default, only the user that registers DevOps Connect is authorized to use it. An authorized user can authorize other users to use the application. Authorized users can access the DevOps Connect web-based dashboard and install plug-ins and create integrations.

1.   [Download DevOps Connect from the IBM developerWorks](https://developer.ibm.com/urbancode/plugin/ibm-urbancode-sync/). The downloaded file is an executable JAR file. You run this file to start DevOps Connect.
2.   Open a command window where you placed the JAR file and start DevOps Connect by using the following command: `java -jar devops-connect-build\_number.jar`. For example, `java -jar devops-connect-2.0.854198.jar`. DevOps Connect displays start-up messages in the command window.
3.   If you use a proxy, use this command to start DevOps Connect: `java -Dhttp.proxyHost=proxy_ip -Dhttp.proxyPort=proxy_port -jar cloud-sync-build_number.jar`. If you use a proxy and SSL, use this command: `java -Dhttps.proxyHost=proxy_ip -Dhttps.proxyPort=proxy_port -jar cloud-sync-build_number.jar`. The following is an example of a typical command: `java -Dhttps.proxyHost=10.0.0.100 -Dhttps.proxyPort=8800 -jar cloud-sync-1.0.787256.jar`. 
4.   After DevOps Connect starts, use a web browser to access the application dashboard. The default URL is https://localhost:8443. You can change the port when you start the utility. For example, to change the port to `8444`, use this command to run the JAR file: `java -Dserver.port=8444 -jar devops-connect.jar`.
5.   On the registration page, if you are prompted to specify a name for the installation, provide a name. This name identifies the data from the installation in other places. 
6.   Click **Register**. The first time that you access DevOps Connect, you are prompted to register.
7.   On the Sign-in to IBM page, enter your IBMid and password, and then click **Sign In**. The DevOps Connect dashboard is displayed. The email address of the user that registers the utility is saved in the `sync.registrar` property in the sync.properties file. Authorized users sign in each time they start the application.
8.   Click **Settings** and then, in the **Allowed Users** text box, enter the email addresses of users who are authorized to access the DevOps Connect dashboard. Separate addresses with commas. You can use the asterisk \(\*\) wildcard character in the email addresses. For example, the pattern `*@.my_company.com` allows any user at `my_company.com` who has an IBMid to access the dashboard. Authorized users can install plug-ins and create integrations. The IBMid of the person who registered DevOps Connect is automatically authorized. The email addresses are saved in the `sync.user` property in the sync.properties file.
9.   To run DevOps Connect as a service on Linux, create a symlink from the DevOps Connect jar file to the init.d program. For example: `$ sudo ln -s /var/myapp/cloud-sync-build_number.jar /etc/init.d/myapp`. After you configure the application, you can use the standard service commands to manage DevOps Connect: `start`, `stop`, `restart`, and `status`. 

After you register, DevOps Connect generates a unique ID and saves it in the `sync.ID` property in the sync.properties file. The token that it receives from the IBM Cloud service is saved in the `sync.token` property. The token and ID identify the DevOps Connect instance.

The plug-ins for IBM UrbanCode Release and IBM UrbanCode Deploy are already installed when you download the utility. Create integrations for one or both of the products.

You can use values in the /home/my\_directory/.ibm/cloud-sync/sync.properties file to manage various aspects of DevOps Connect. This table describes the available properties.

|Property|Description|
|--------|-----------|
|`sync.installation.dir`|Directory where the devops-connect.jar file is located.|
|`sync.id`|Unique identifier that is used to authenticate DevOps Connect to the IBM Bluemix services. This property should not be modified.|
|`sync.name`|Optional name for the DevOps Connect instance. The name property can be used by IBM Bluemix services that integrate with multiple DevOps Connect instances.|
|`sync.token`|Unique identifier that is generated by IBM Bluemix services and used to authenticate DevOps Connect. This property should not be modified.|
|`sync.registrar`|IBMid of the user who registered DevOps Connect. This property should not be modified.|
|`sync.users`|Comma-delineated list of users who are authorized to use the DevOps Connect dashboard. This property should not be directly modified. Use the dashboard **Settings** tab to manage authorized users.|
|`sync.port`|DevOps Connect port number. If you set this property, you do not have to use the command line parameter when you start the application.|
|`http.proxyHost`|Proxy host URL. If you use a proxy, set this property and the `http.proxyPort` property.|
|`http.proxyPort`|Proxy port number.|

**Parent topic:** [Integrating with cloud and mobile services with IBM BluemixIBM DevOps Connect](../topics/installIntegrate_UCR_cloud_cp.md)

