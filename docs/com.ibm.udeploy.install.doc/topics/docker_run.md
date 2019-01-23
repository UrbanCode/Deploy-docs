# Accessing the server in an ICP cluster

Ensure that the UrbanCode Deploy server has been properly installed in your IBM® Cloud Private environment. 

This topic describes how to access a running instance of the UrbanCode Deploy server installed in an IBM Cloud Private cluster.

1.   On your IBM Cloud Private dashboard, select **Menu** \> **Workloads** \> **Helm Releases** and click the name of your Helm release. 
2.   On the Helm release page, select the instance name in the **StatefulSet** or **Pod** areas. Information is displayed about the pod where the HCL® UrbanCode™ Deploy server is running.

    Wait until the value of the **Ready** property is `1/1` before accessing the server. The pod is ready when the **Service** section displays the HTTPS ports for the UrbanCode Deploy server. You can also see the ports by running the commands displayed in the **Notes** area.

3.   Using a web browser, log onto the server at the specified URL, `https://cluster-proxy-host:node-port`. The default initial credentials are ID: `admin`, password: `admin`. Click **Menu-\>Platform-\>Nodes** to see the cluster-proxy-host. Look for the node with the role of proxy.

After you log on to your HCL UrbanCode Deploy server, set the **External Agent URL** and **External User URL** properties on the **Settings-System Settings** page. The value is the same URL value you used to log in to the server.

[If you run into problems, visiting the Troubleshooting page.](https://developer.ibm.com/urbancode/docs/urbancode-deploy-container-troubleshooting/)


