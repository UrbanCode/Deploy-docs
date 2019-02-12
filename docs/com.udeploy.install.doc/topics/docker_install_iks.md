# Installing the server in IBM Cloud Kubernetes Service

You can install a containerized version of the HCL® UrbanCode™ Deploy server in an IBM Cloud Kubernetes Service. The UrbanCode Deploy server is installed using a Helm chart. After the server is installed, you can manage it with the ICP Management console.

Prior to installing UrbanCode Deploy, the following prerequisites must be met.

|Prerequisite|Description|
|------------|-----------|
|Prepare your IBM Cloud Kubernetes Service cluster.|[Configure the cluster](https://console.bluemix.net/docs/containers/container_index.html#container_index)|
|To install the server image using the Helm command-line client, install kubectl and then set up the Helm CLI \(command line interface\).| [Install and set up kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)

 [Install and set up the Helm CLI](https://www.ibm.com/support/knowledgecenter/SSBS6K_3.1.0/app_center/create_helm_cli.html)

 |
|The containerized server, like the on-premises version, requires a database. The database can be installed in any location that can be accessed by the cluster, such as an on-premise location or in a cluster.|[Install database](https://www.ibm.com/support/knowledgecenter/SS4GSP_7.0.0/com.ibm.udeploy.install.doc/topics/DBinstall.html).**Note:** Unlike the on-premises version of HCL UrbanCode Deploy, the containerized version does not support the Apache Derby database.

|
|The installation material consists of an IBM Passport Advantage archive \(PPA\) file, that contains a Docker image and a Helm chart. Helm is the Kubernetes package management tool. Helm charts are packages similar to debs and rpms packages. Download the PPA file for your operating system from the IBM Passport Advantage website. PPA files are available for x86, Z Linux systems and PowerPC \(LE\).|[Load PPA archive file](https://www.ibm.com/support/knowledgecenter/en/SSBS6K_3.1.0/manage_cluster/cli_catalog_commands.html#load-archive)|
|Two persistent volumes are required for Urban Code Deploy. One volume holds the JDBC driver or drivers and the other contains the server's /appdata directory.If your Kubernetes cluster does NOT support dynamic persistent volumes, you need to manually create and set up storage volumes in your cluster.

**Note:** If your Kubernetes cluster supports dynamic storage provisioning, this prerequisite is not required. Storage is automatically managed.

|[Create persistent volumes](https://www.ibm.com/support/knowledgecenter/SSBS6K_3.1.0/manage_cluster/create_volume.html)|
|Copy the JDBC drivers to the extLib persistent volume created in your Kubernetes cluster.| Use a `ConfigMap` to copy the JDBC files into the persistent volume.

 This sample YAML file describes a ConfigMap resource with a shell script, named script.sh. The script performs a `wget` command to pull the MySQL.jar file from a web server and copy it to the `${UCD_HOME}/ext_lib/` directory in the container. In order for the image initialization code to find and execute the script, the script **must** be named script.sh.

 ```
kind: ConfigMap
apiVersion: v1
metadata:
  name: user-script
data:
  script.sh: |
    #!/bin/bash
    echo "Running script.sh..."
    if [ ! -f ${UCD_HOME}/ext_lib/mysql-jdbc.jar ] ; then
      which wget
      if [ $? -ne 0 ]; then
        apt-get update -y
        echo "Installing wget..."
        apt-get install wget -y
      fi
      echo "Copying file(s)..."    
      wget http://hostname/ucd-extlib/mysql-jdbc.jar
      mv mysql-jdbc.jar ${UCD_HOME}/ext_lib/
      echo "Done copying."
    else
      echo "File ${UCD_HOME}/ext_lib/mysql-jdbc.jar already exists."
    fi

```

 To create your own ConfigMap, make a copy using the copy icon provided, place the content in a file called userscript.yaml and run the following command:

 kubectl apply -f user-script.yaml

 |

This task installs the containerized version of the HCL UrbanCode Deploy server in an IBM Cloud Kubernetes Service \(IKS\) cluster. After the server is installed, you can manage it with the ICP Management console.

1.   Complete the steps in **Before you begin**. 
2.   Perform the following actions to use the UrbanCode Deploy image. 
    1.   Download the archive from Passport Advantage. 
    2.   From the downloaded UrbanCode Deploy image archive, eExtract the archive with `tar -xzf [archive]`. 
    3.   In the `images` folder, load the image archive to Docker with `docker image load -i [image archive]`. 
    4.   Tag and push the image to the Docker registry of your choice. 
3.   Perform the following actions to use the UrbanCode Deploy Helm chart. 
    1.   Extract the archive with `tar -xzf [archive]`. 
    2.   In the `charts` folder, extract the chart archive with `tar -xzf [chart archive]`. The chart is found in the `ibm-ucd-prod` directory. 
    3.   Copy `values.yaml` file. Name the copied file `myvalues.yaml`. Edit `myvalues.yaml` to specify values for your installation. Refer to the README.md file for details. 
4.   Install the Helm chart with the release name my-ucd-release and connect to the specified database. 

    ```
    $ helm install --name my-ucd-release -f myvalues.yaml ibm-ucd-prod
    ```

    This command sets database parameters. Other parameters may also be required. If parameters aren't specified with the `--set` flag, their values will default to the values specified in the values.yaml file.

    Refer to [Helm chart configuration parameters](docker_helmparametersdita.md#) for a list of the parameters that can be set during installation.

5.   See NOTES.txt associated with this chart for verification instructions. 

    Use the following command to uninstall and delete the my-ucd-release deployment.

    ```
    $ helm delete --purge --tls my-ucd-release
    ```

    The command removes all the Kubernetes resources associated with the chart and deletes the release.


Access your containerized instance of HCL UrbanCode Deploy.

-   **[Accessing the server in an IKS cluster](../../com.udeploy.install.doc/topics/docker_runIKS.md)**  
This topic contains the instructions that are used to access and start the UrbanCode Deploy server in the Kubernetes cluster via the IBM® Cloud Kubernetes Service.

**Parent topic:** [Installing the server in a Kubernetes cluster](../../com.udeploy.install.doc/topics/docker_cloud_over.md)

**Related information**  


[Helm chart configuration parameters](docker_helmparametersdita.md#)

