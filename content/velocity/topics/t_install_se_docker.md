# Installing UrbanCode Velocity with Docker Compose {#t_install_se_docker .task}

Instructions for installing UrbanCode® Velocity into the Docker Compose container orchestrator.

Review the [System requirements](c_install_se_requirements.md#) before starting. In addition to the requirements for all installation scenarios, the following items are required for Docker Compose systems:

-   Docker Compose version 17.09.0-ce, build afdb6d4 and later
-   CPU with 4+ cores.
-   8GB RAM
-   8GB storage

[Download the installation file](https://github.com/IBM/velocity-se/releases). Because files are retrieved from GitHub and Docker Hub during installation, you must have an Internet connection when installing the product.

In addition, make sure that UrbanCode Velocity can access your UrbanCode Deploy server.

The installation instructions describe installing the product in the Windows and Linux™ operating systems. Run the downloaded executable, `velocity-install-docker-compose-win.exe`, and then complete installation by responding to the prompts.

1.   At the **Choose a version** prompt, select the product version to install. 
2.   At the **Please enter your Velocity access key** prompt, enter your SE version access key. If you previously installed an SE version, the already-configured key is the default value.
3.   At the **Please enter the hostname where you will run Velocity** prompt, enter the host name where users can access the Web UI. The default value is `localhost`.
4.   At the **Enter the desired port where Velocity will run** prompt, enter the port number for the Web UI. The default value is `443`.
5.   At the **Enter the location where the Velocity files will be installed** prompt, enter the location where you want to install the product 
6.   Complete installation by running the following command: 

    ```
    docker-compose up -d
    ```

    The UrbanCode Velocity images are pulled from Docker Hub configured for Docker Compose.


Access the UrbanCode Velocity Web UI. The URL is https://hostname:port, where `hostname` and `port` are the values that you set during installation. The initial user name is admin and the default password is admin.

Installation properties are stored in the \[installation\_folder\]\\.env file. You can edit the properties appropriate for your environment. The env file contains a description for all installation properties, including the following properties:

 Access\_Key
 :   The product access key obtained from Passport Advantage.

  NGINX\_HOST
 :   The domain of the URL the users will use to access Velocity. The value is usually the hostname of the VM that Docker Compose is running on.

 **Parent topic:** [Installation roadmap](../topics/c_install_se_roadmap.md)

