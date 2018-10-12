# Uninstalling the server {#t_install_se_remove_ucv .task}

You can uninstall UrbanCode Velocity by stopping the server and removing the product containers.

Data is not affected when removing the containers as long as your volume is persistent. Uninstalling the product is necessary when you have a new version of the product images that you want to install.

Remove the product using the appropriate command listed below.

-   Docker Compose

    ```
    
    docker-compose stop
    docker-compose rm
    ```

-   Kubernetes

    ```
    helm delete velocity-se --purge
    ```


**Parent topic:** [Installation roadmap](../topics/c_install_se_roadmap.md)

