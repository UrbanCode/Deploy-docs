# Accessing the server in an IKS cluster

This topic contains the instructions that are used to access and start the UrbanCode Deploy server in the Kubernetes cluster via the IBM® Cloud Kubernetes Service.

Ensure that the UrbanCode Deploy server has been properly installed in your IBM Cloud Kubernetes Service environment. 

This topic describes how to access a running instance of the UrbanCode Deploy server installed in an IKS cluster.

1.   The output of the Helm install command includes a NOTES section that provides commands for obtaining the URL used to access the UrbanCode Deploy server.  

    ```
    NOTES:
    1. Get the application URL by running these commands:
      export NODE_PORT=$(kubectl get --namespace default -o jsonpath="{.spec.ports[0].nodePort}" services tneal-ucd2-ibm-ucd-prod)
      export NODE_IP=$(kubectl get nodes --namespace default -o jsonpath="{.items[0].status.addresses[0].address}")
      echo https://$NODE_IP:$NODE_PORT
    ```

    Run the commands in the NOTES section to obtain the URL used to access the UrbanCode Deploy server.

2.   Using a web browser, log onto the server at specified URL, `https://cluster-proxy-host:node-port`. The default initial credentials are ID: `admin`, password: `admin`. Click **Menu-\>Platform-\>Nodes** to see the cluster-proxy-host. Look for the node with the role of proxy.

After you log on to your HCL UrbanCode Deploy server, set the **External Agent URL** and **External User URL** properties on the **Settings-\>System Settings** page. The value is the same URL value you used to log in to the server.

If you run into problems, visit the [Troubleshooting](https://developer.ibm.com/urbancode/docs/urbancode-deploy-container-troubleshooting/) page.



