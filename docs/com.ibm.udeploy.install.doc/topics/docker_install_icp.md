# Installing the server in IBM Cloud Private

You can install a containerized version of the HCL® UrbanCode™ Deploy server in an IBM Cloud Private \(ICP\) cluster. The UrbanCode Deploy server is installed using a Helm chart. After the server is installed, you can manage it with the ICP Management console.

The containerized version of UrbanCode deploy is compatible with IBM Cloud Private versions 2.1.0.2 and later. Prior to installing UrbanCode Deploy, the following prerequisites must be met.

|Prerequisite|Description|
|------------|-----------|
|Prepare your IBM Cloud Private cluster|[Install IBM Cloud Private](https://www.ibm.com/support/knowledgecenter/SSBS6K_3.1.0/kc_welcome_containers.html)|
|Install the ICP command line client.|[Install ICP command line client](https://www.ibm.com/support/knowledgecenter/SSBS6K_3.1.0/manage_cluster/install_cli.html)|
|If you want to install the server image using the Helm command-line client instead of the ICP user interface, install kubectl and then set up the Helm CLI \(command line interface\).| [Install and set up kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)

 [Install and set up the Helm CLI](https://www.ibm.com/support/knowledgecenter/SSBS6K_3.1.0/app_center/create_helm_cli.html)

 |
|The containerized server, like the on-premises version, requires a database. The database can be installed in any location that can be accessed by the cluster, such as an on-premise location or in a cluster.|[Install database](https://www.ibm.com/support/knowledgecenter/SS4GSP_7.0.0/com.ibm.udeploy.install.doc/topics/DBinstall.html).**Note:** Unlike the on-premises version of HCL UrbanCode Deploy, the containerized version does not support the Apache Derby database.

|
|The installation material consists of an IBM Passport Advantage® archive \(PPA\) file, that contains a Docker image and a Helm chart. Helm is the Kubernetes package management tool. Helm charts are packages similar to debs and rpms packages. Download the PPA file for your operating system from the IBM Passport Advantage website. PPA files are available for x86, Z Linux® systems and PowerPC® \(LE\). Typically, your cluster administrator loads the PPA file into ICP using a CLI command \(cloudctl catalog load-archive\), that installs the Docker image and the Helm chart.

|[Load PPA archive file](https://www.ibm.com/support/knowledgecenter/en/SSBS6K_3.1.0/manage_cluster/cli_catalog_commands.html#load-archive)**Note:** If your cluster administrator has not loaded the Helm chart and Docker image, you can perform this from a command line.

|
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

This task consists of defining parameters for the Helm chart and initiating its installation.

1.   Complete the steps in **Before you begin**. 
2.   Complete the following actions for the Helm chart. 
    1.   Open the Dashboard for your IBM Cloud Private instance. 
    2.   On the task bar, select **Catalog** \> **Helm charts**, filter the list on `ucd`, then select the Helm chart that you loaded, **ibm-ucd-prod**. 
    3.   On the Helm Chart README page, review the chart's properties using the tool tips provided.
    4.   Click **Configure**, and then define the chart properties. Most properties have default values already defined. See [Helm chart configuration parameters](docker_helmparametersdita.md#).
3.   Click **Install**. A Helm release is created for an instance of the HCL UrbanCode Deploy server in your cluster.
4.   Click **View Helm Release** to view information about your HCL UrbanCode Deploy instance. 
5.   Use the following command to uninstall and delete the my-ucd-release deployment. The command removes all the Kubernetes resources associated with the chart and deletes the release. 

    ```
    $ helm delete --purge --tls my-ucd-release
    ```


Access your containerized instance of HCL UrbanCode Deploy.

-   **[Accessing the server in an ICP cluster](../../com.ibm.udeploy.install.doc/topics/docker_run.md)**  


**Parent topic:** [Installing the server in a Kubernetes cluster](../../com.ibm.udeploy.install.doc/topics/docker_cloud_over.md)

**Related information**  


[Helm chart configuration parameters](docker_helmparametersdita.md#)

