# Helm chart configuration parameters

The Helm chart has the following values that can be overridden using the --set parameter.

|Qualifier|Parameter|Definition|Allowed Value|
|---------|---------|----------|-------------|
|arch| |The desired worker node architecture|amd64, s390x, or ppc64le|
|image|pullPolicy|Image Pull Policy|Always, Never, or IfNotPresent. Defaults to Always|
| |repository|Name of image, including repository prefix \(if required\)|See [Extended description of Docker tags](https://docs.docker.com/engine/reference/commandline/tag/#extended-description)|
| |tag|Docker image tag|See [Docker tag description](https://docs.docker.com/engine/reference/commandline/tag/)|
| |secret|An image pull secret used to authenticate with the image registry|Empty \(default\) if no authentication is required to access the image registry.|
|service|type|Specify type of service|Valid options are NodePort and LoadBalancer \(for clusters that support LoadBalancer\). Default is NodePort|
|database|type|The type of database UCD will connect to|Valid values are db2, db2zos, mysql, mariadb, oracle, and sqlserver|
| |name|The name of the database to use| |
| |hostname|The hostname/IP of the database server| |
| |port|The database port to connect to| |
| |username|The user to access the database with| |
| |password|The password of the database user| |
|secureConnections|required|Specify whether UCD server connections are required to be secure|Default value is "true"|
|security|ucdInitPassword|The admin password for the UCD UI|Default value is "admin"|
|extLibVolume|name|The base name used when the Persistent Volume and/or Persistent Volume Claim for the extlib directory is created by the chart.|Default value is "ext-lib"|
| |storageClassName|The name of the storage class to use when persistence.useDynamicProvisioning is set to "true".| |
| |size|Size of the volume used to hold the JDBC driver .jar files| |
| |existingClaimName|Persistent volume claim name for the volume that contains the JDBC driver file\(s\) used to connect to the UCD database.| |
| |configMapName|Name of an existing ConfigMap which contains a script named script.sh. This script is run before UrbanCode Deploy server installation and is useful for copying database driver .jars to a Persistent Volume.| |
|persistence|enabled|Determines if persistent storage will be used to hold the UCD server appdata directory contents. This should always be true to preserve server data on container restarts.|Default value "true"|
| |useDynamicProvisioning|Set to "true" if the cluster supports dynamic storage provisoning|Default value "false"|
|appDataVolume|name|The base name used when the Persistent Volume and/or Persistent Volume Claim for the UCD server appdata directory is created by the chart.|Default value is "appdata"|
| |existingClaimName|The name of an existing Persistent Volume Claim that references the Persistent Volume that will be used to hold the UCD server appdata directory.| |
| |storageClassName|The name of the storage class to use when persistence.useDynamicProvisioning is set to "true".| |
| |size|Size of the volume to hold the UCD server appdata directory| |
|resources|constraints.enabled|Specifies whether the resource constraints specified in this helm chart are enabled.|false \(default\) or true|
| |limits.cpu|Describes the maximum amount of CPU allowed|Default is 2000m. See Kubernetes - [meaning of CPU](https://kubernetes.io/docs/concepts/configuration/manage-compute-resources-container/#meaning-of-cpu)|
| |limits.memory|Describes the maximum amount of memory allowed|Default is 2Gi. See Kubernetes - [meaning of Memory](https://kubernetes.io/docs/concepts/configuration/manage-compute-resources-container/#meaning-of-memory)|
| |requests.cpu|Describes the minimum amount of CPU required - if not specified will default to limit \(if specified\) or otherwise implementation-defined value.|Default is 1000m. See Kubernetes - [meaning of CPU](https://kubernetes.io/docs/concepts/configuration/manage-compute-resources-container/#meaning-of-cpu)|
| |requests.memory|Describes the minimum amount of memory required If not specified, the memory amount will default to the limit \(if specified\) or the implementation-defined value|Default is 1Gi. See Kubernetes - [meaning of Memory](https://kubernetes.io/docs/concepts/configuration/manage-compute-resources-container/#meaning-of-memory)|
|readinessProbe|initialDelaySeconds|Number of seconds after the container has started before the readiness probe is initiated|Default is 30|
| |periodSeconds|How often \(in seconds\) to perform the readiness probe|Default is 30|
| |failureThreshold|When a Pod starts and the probe fails, Kubernetes will try this number times before giving up. In the case of the readiness probe, the Pod will be marked Unready.|Default is 10|
|livenessProbe|initialDelaySeconds|Number of seconds after the container has started before the liveness probe is initiated|Default is 300|
| |periodSeconds|How often \(in seconds\) to perform the liveness probe|Default is 300|
| |failureThreshold|When a Pod starts and the probe fails, Kubernetes will try this number times before giving up. Giving up in the case of the liveness probe means restarting the Pod.|Default is 3|

**Parent topic:** [Installing the server in a Kubernetes cluster](../../com.udeploy.install.doc/topics/docker_cloud_over.md)

