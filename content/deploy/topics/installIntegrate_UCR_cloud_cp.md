# Integrating with cloud and mobile services with IBM BluemixIBM DevOps Connect {#installIntegrate_UCR_cloud_cp .concept}

IBM® Bluemix®IBM DevOps Connect coordinates communication between IBM UrbanCode® Release, IBM UrbanCode Deploy, and the IBM Cloud and Bluemix services.

You download DevOps Connect from IBM developerWorks, and install it on a computer that has access to IBM UrbanCode Release or IBM UrbanCode Deploy. DevOps Connect comes with several plug-ins installed that you can use to integrate IBM UrbanCode Release and IBM UrbanCode Deploy with IBM Cloud and Bluemix services. You can update existing plug-ins or [install new ones by using the DevOps Connect web-based dashboard](installIntegrate_UCR_cloud_plugin.md#).

You can start creating integrations with the installed plug-ins as soon as you register for DevOps Connect. DevOps Connect includes the following plug-ins:

-   **IBM UrbanCode Deploy for Mobile**. This plug-in provides IBM UrbanCode Deploy data to IBM UrbanCode Mobile users.
-   **IBM UrbanCode Release for Mobile**. This plug-in provides IBM UrbanCode Release data to IBM UrbanCode Mobile users.
-   **IBM UrbanCode Deploy for Cloud Reporting**. This plug-in sends data from DevOps Connect to Delivery Insights.

After you install DevOps Connect, use the installed plug-ins to create integrations with IBM UrbanCode Release and IBM UrbanCode Deploy. Integrations run periodically and sync data between the integrated products and the IBM Bluemix services. Integrations use encrypted SSL connections and store data in encrypted databases. DevOps Connect encrypts the data before it provides it to the IBM Bluemix services.

The first time that you run DevOps Connect, register it by using your IBMid. You cannot use DevOps Connect until you register it. DevOps Connect generates a unique ID and receives a token that together forms its credentials. The credentials are used to establish secure connections and store configuration information and data in the cloud. The credentials are stored in the sync.properties file. For information about the sync.properties file, see [Installing IBM BluemixIBM DevOps Connect](installIntegrate_UCR_sync.md#).

DevOps Connect uses SSL to communicate with the cloud services. The DevOps Connect web-based dashboard also uses SSL.

-   **[Installing IBM BluemixIBM DevOps Connect](../topics/installIntegrate_UCR_sync.md)**  
Install IBM BluemixIBM DevOps Connect to share data between IBM UrbanCode Deploy, IBM UrbanCode Release, and IBM UrbanCode Cloud services and Bluemix Services.
-   **[Installing plug-ins into IBM BluemixIBM DevOps Connect](../topics/installIntegrate_UCR_cloud_plugin.md)**  
Install and upgrade plug-ins in IBM BluemixIBM DevOps Connect.
-   **[Integrating IBM UrbanCode Deploy with UrbanCode Mobile](../topics/installIntegrate_UCD_cloud_sync.md)**  
Use IBM Bluemix DevOps Connect to integrate IBM UrbanCode Deploy with UrbanCode Mobile.
-   **[Configuring the UrbanCode Mobile app](../topics/installIntegrate_UCR_mobile.md)**  
Connect your UrbanCode Mobile application to the IBM Cloud service and receive deployment data on your mobile devices.

