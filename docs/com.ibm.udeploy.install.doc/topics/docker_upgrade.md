# Upgrading the containerized server

You can upgrade your containerized version of the HCL® UrbanCode™ Deploy server 6.2.7 to the 7.0.0 version in an IBM® Cloud private and IBM Cloud Kubernetes Service cluster.

Log in to the IBM Cloud Private cluster where your UrbanCode Deploy server container is running.

The IBM Cloud Private cluster administrator will need to follow the directions for loading the Passport Advantage® archive file for the containerized UCD 7.0.0 product. For more information see “Installing bundled products” at [https://www.ibm.com/support/knowledgecenter/SSBS6K\_2.1.0.3/installing/install\_entitled\_workloads.html](https://www.ibm.com/support/knowledgecenter/SSBS6K_2.1.0.3/installing/install_entitled_workloads.html)

**Note:** Contact UrbanCode Deploy Technical Support for instructions for upgrading the containerized version of the HCL UrbanCode Deploy server from 7.0.0 to 7.0.1.

1.   Once logged in, go to **Workloads \> Helm Releases** in the upper left corner of the screen. 
2.   Find the Helm release that is associated with your UrbanCode Deploy server. 
3.   On the far right of the line showing your Helm release, click the ellipsis in the **Action** column, then select **Upgrade**. 
4.   Once on the Upgrade screen, specify the version of the Helm chart you want to use for the upgrade \(2.0 is the latest version of the Helm chart for UrbanCode Deploy 7.0\), then fill in the values for the fields in the chart. Specify the UrbanCode Deploy server image tag you want to use as 7.0.0.0.982083. 
5.   Click **Upgrade**. 

After install is complete, your existing instance of UrbanCode Deploy server will be stopped, and then the new instance will be started using the values you specified, including using the new UrbanCode Deploy 7.0 image. All upgrade actions will be taken care of automatically \(database upgrade, etc\). Support for UrbanCode Deploy 7.0 agent communications using WebSocket Secure \(WSS\) is enabled by default. Optionally, you can select added support for logging and metering.

**Parent topic:** [Installing the server in a Kubernetes cluster](../../com.ibm.udeploy.install.doc/topics/docker_cloud_over.md)

