# Adding blueprint design servers to clusters {#ha_add_bds .task}

To add a blueprint design server to a cluster, connect it to the shared database and network storage. Then, configure the load balancer to send traffic to it.

-   Set up a cluster of blueprint design servers, including setting up a load balancer, shared database, and network storage. See [Setting up clusters of blueprint design servers](ha_config_bds.md).
-   Each blueprint design server must run the same version of IBM® UrbanCode® Deploy.

You can add many blueprint design server nodes to the cluster as you need. Each node includes the blueprint designer and the cloud discovery service.

1.   On the new node, install the blueprint design server as described in [Installing the blueprint design server](../../com.ibm.udeploy.install.doc/topics/install_server_bds.md), with the following settings. 

    -   For the public address of the system, specify the IP address of the load balancer.
    -   Do not use SSL encryption.
    -   When asked whether you want to create the database schema, say yes if this is the first blueprint design server node or no if it is not.
    -   For the database, specify the shared blueprint design server database.
    **Important:** Do not start the blueprint design server or cloud discovery service yet.

2.   Mount the shared folders on the network storage to the following locations: 

    -   /opt/ibm-ucd-patterns/repositories
    -   /opt/ibm-ucd-patterns/workspace
    For example, if you are using NFS for the network storage on the `nfs-host.example.com` host name, run the following commands to install NFS and mount the shared folders:

    1.  ```
yum -y install nfs-utils nfs-utils-lib
```

    2.  ```
service rpcbind start
```

    3.  ```
chkconfig nfs on
```

    4.  ```
service nfs start
```

    5.  ```
mount -t nfs
          nfs-host.example.com:/opt/ibm-ucd-patterns/workspace /opt/ibm-ucd-patterns/workspace
```

    6.  ```
mount -t nfs
          nfs-host.example.com:/opt/ibm-ucd-patterns/repositories /opt/ibm-ucd-patterns/repositories
```

    Then, verify that the folders are mounted by running the following command:

    ```
    mount | grep nfs
    ```

    If the node cannot access the folders, make sure that the node is authorized to access the folders in the /etc/exports file on the network storage.

3.   Set the new server to use the same security certificate as the existing servers. For example, you can copy the certificate in the /opt/tomcat/conf/tomcat.keystore file to the other servers. When you import the certificate into other servers, in the server.xml file, set the keyAlias property to point to the imported certificate.
4.   Start the cloud discovery service. 
5.   Start the blueprint designer. 
6.   Configure the load balancer to send traffic on the following ports to the new node: 

    -   8080, or the HTTP port that you specified when you installed the blueprint design server
    -   7575, for the cloud discovery service
    For example, if you are using HAProxy, the configuration file might have code that is similar to the following snippets. In this code, it is assumed that the blueprint design server nodes have these host names: `designer1.example.com`, `designer2.example.com`, and `designer3.example.com`.

    ```
    frontend ucdp
        bind *:8080
        default_backend ucdp_back
    
    frontend cds
        bind *:7575
        default_backend cds_back
    ```

    ```
    
    backend ucdp_back
        balance     roundrobin
        server      designernode1 designer1.example.com:8080 check
        server      designernode2 designer2.example.com:8080 check
        server      designernode3 designer3.example.com:8080 check
        option      httpchk OPTIONS /
        option      forwardfor
        option      http-server-close
        appsession JSESSIONID len 52 timeout 3h
    
    backend cds_back
        balance     roundrobin
        server      designernode1 designer1.example.com:7575 check
        server      designernode2 designer2.example.com:7575 check
        server      designernode3 designer3.example.com:7575 check
        option      httpchk
    
    ```

7.   Verify that the load balancer is sending traffic to the new node. For example, if HAProxy is installed on a system with the host name `ucd-patterns.example.com`, you can go to the following URL to see the status of the nodes: `http://ucd-patterns.example.com:1936/haproxy?stats` 
8.   Verify that the new blueprint designer node is connected to the cluster by creating a blueprint and verifying that the blueprint is included on the network storage. 
    1.   Go to `http://ucd-patterns.example.com:8080/landscaper` in a web browser. 
    2.   In the default repository, create a blueprint, and verify that you can edit the blueprint. 
    3.   On the network storage, find the blueprint file to verify that it is stored on the network storage. The default location for blueprints in the default repository is /opt/ibm-ucd-patterns/workspace/repositories/initials/username\_userid/OrionContent/default, where:
        -   initials is the first two letters of the user name
        -   username is the user name that you used to create the blueprint
        -   userid is the unique ID of the user
    4.   In the Internal-Team repository, create another blueprint. 
    5.   On the network storage, find the blueprint file to verify that it is stored on the network storage. The default location for blueprints in the Internal-Team repository is /opt/ibm-ucd-patterns/workspace/repositories/initials/username\_userid/OrionContent/Internal-Team, where:
        -   initials is the first two letters of the user name
        -   username is the user name that you used to create the blueprint
        -   userid is the unique ID of the user
    6.   On the **Repository** tab, push the new Internal-Team blueprint to the team repository. 
    7.   Verify that the blueprint exists in the Gitblit repository by going to the URL `http://ucd-patterns.example.com:8080/gitblit/summary/Internal-Team.git` in a web browser. The default user name and password are `gitadmin`.

The blueprint design server is part of the cluster.

