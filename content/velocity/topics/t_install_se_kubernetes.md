# Installing into a Kubernetes cluster {#t_install_se_kubernetes .task}

It is important that you review the [System requirements](c_install_se_requirements.md) before starting.

Before starting installation, ensure that the following applications are installed in the target environment:

-   Kubernetes 1.4+ with Beta APIs enabled
-   MongoDB database with persistent volume
-   RabbitMQ
-   Helm v2.6.0 or later.

You will install UrbanCode™ Velocity into a Kubernetes cluster using Helm commands. The commands pull the UrbanCode Velocity node images from a GitHub repository and places them into the Kubernetes clusters defined in Helm Charts.

1.   Clone the UrbanCode Velocity repository. 

    ```
    git clone https://github.com/IBM/velocity-se
    ```

2.   Issue the following command to obtain the Helm charts used for the installation. 

    ```
    
    $ helm init
    $ helm repo add urbancode-se https://raw.githubusercontent.com/IBM/velocity-se/master/kubernetes/repo
    $ helm repo add ibm-stable https://raw.githubusercontent.com/IBM/charts/master/repo/stable/
    $ helm repo update
    ```

3.   If you do not have a MongoDB database installed, you can install one now. Go to [MongoDB](https://github.com/kubernetes/charts/tree/master/stable/mongodb) GitHub repository to install. Below is a sample command for installing the MongoDB. Based on your environment, you might need to modify or add to the sample command.

    ```
    
    helm install   \
       --set database.password=mongo \
       --set database.user=mongo \
       --set database.name=velocity \
       --name velocity-mongo ibm-stable/ibm-mongodb-dev
    ```

4.   If you do not have a RabbitMQ server installed, you can install one now. 

    Issue the following command to install a RabbitMQ.

    ```
    
    helm install  \
     --set rabbitmq.username=rabbit \
     --set rabbitmq.password=carrot  \
     --name velocity-rabbitmq urbancode-se/rabbitmq
    ```

5.   Determine the configuration properties to specify. You can customize the installation by specifying configuration properties on the helm install command. 

    Some of the properties that you specify are dependent on your environment. However, there are several properties that must be specified. Below are the required properties.

     access.key
     :   The product access key obtained from Passport Advantage.

      apitoken
     :   A random string or GUID that is used verify the authenticity of API calls and data.

      ciphertoken
     :   A 32-byte Hex that is used verify the authenticity of API calls and data.

      hamackey
     :   A 32-byte Hex that is used verify the authenticity of API calls and data.

      loglevel
     :   The level of logging. Values for this property are: all, debug, info, warn, error, fatal, and off. The default is **all**.

      mongo.url
     :   The URL of the MongoDB. Specify the following parameters.

         username
         :   The user ID to authenticate with the MongoDB database.

          password
         :   The associated password to authenticate with the MongoDB database.

          port
         :   The port number for the MongoDB database. Use the value shown in the example, which is 27017.

          service\_name
         :   The MongoDB URL or the MongoDB service name if it is running within the Kubernetes cluster.

          database\_name
         :   The name of the database to be used by UrbanCode Velocity.

         **Note:** If you used the install command in the previous step to install the MongoDB, use the following values for the **mongo.url** property.

        ```
        mongodb://mongo:mongo@velocity-mongo-ibm-mongodb-dev:27017/admin
        ```

      rabbit.url
     :   The URL of the RabbitMQ installed in the previous step. Specify the following parameters.

         username
         :   The user ID to authenticate with the RabbitMQ server.

          password
         :   The associated password to authenticate with the RabbitMQ server.

          port
         :   The port number for the RabbitMQ server. Use the value shown in the example, which is 5672.

          service\_name
         :   The RabbitMQ URL or the RabbitMQ service name if it is running within the Kubernetes cluster.

         **Note:** If you used the install command in the previous step to install the RabbitMQ server, use the following values for the **rabbitmq.url** property.

        ```
        amqp://rabbit:carrot@velocity-rabbitmq:5672/
        ```

      url.domain
     :   The hostname of your Kubernetes master node or the Ingress host name. If there is a reverse proxy in front of the Kubernetes cluster, it becomes the domain name.

 6.   Run the `helm install` command to install the UrbanCode Velocity images into your Kubernetes cluster. The following example shows the required configuration properties, depending on your environment other might be required. 

    ```
    
    helm install \
    --set access.key=access_key \
    --set url.domain=hostname \
    --set mongo.url=mongodb://mongo:mongo@velocity-mongo-ibm-mongodb-dev:27017/admin \
    --set rabbitmq.url=amqp://rabbit:carrot@velocity-rabbitmq:5672/ \
    --name velocity-se urbancode-se/velocity
    ```


Access the administrator user interface to complete the configuration. Refer to the NOTES section displayed after the `helm install` command completes for the location of the administrator user interface. The user name is admin and the default password is admin.

**Parent topic:** [Installation roadmap](../topics/c_install_se_roadmap.md)

