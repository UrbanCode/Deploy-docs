# Installation roadmap {#c_install_se_roadmap .concept}

The installation roadmap is a description of the high-level steps for installing UrbanCode™ Velocity.

[You can install the free-to-use Community Edition \(CE\)](../../com.ibm.insights.doc/topics/c_install_roadmap.md#), which contains many UrbanCode Velocity features. Or you can install the full-featured Standard Version \(SE\). The SE version is free to use for the first 60 days, at which time you must obtain a license.

UrbanCode Velocity consists of services and other tools that are stored in a Docker container. You can install the container in one of the container orchestrators, Docker Compose, or Kubernetes. You can install the product in any environment that supports the container orchestrators, including bare-metal servers and cloud-based platforms, such as the environments listed here:

-   Windows
-   Linux
-   MacOS
-   IBM Cloud Private
-   IBM Cloud services
-   Amazon Web Services
-   Google

Before starting installation, review the following general steps

1.  **Verify the requirements that apply to all installation scenarios**

    Verify that your computer meets the[minimum hardware and software requirements](c_install_se_requirements.md) for installing the product. Some system requirements affect all installation scenarios while other requirements depend on the container management system that you use.

2.  **Get an access key**

     [Visit the UrbanCode Velocity web portal to get you access key](https://https://uc-velocity.com/). After you create an ID and provide an email address, you can copy the access key. You use the key during installation. Regardless of which product version you install, you need an access key to run the product.

3.  **Download the installation program**

    After you purchase the product, you can obtain an access key and download the installation package from [Passport Advantage](https://www.ibm.com/software/howtobuy/passportadvantage/paocustomer). To obtain the product access key you must agree to the terms and condition statements provided on Passport Advantage. The access key is required to start the install process for the initial and future installations.

    The download package includes the installation program for both Docker Compose and Kubernetes environments.

4.  **Install UrbanCode Velocity for your target environment:**

    [Installing UrbanCode Velocity with Docker Compose](t_install_se_docker.md#).

    [Installing into a Kubernetes cluster](t_install_se_kubernetes.md#).

5.  **Integrate with external tools**

    After the installation is complete, you can access the configuration pages to integrate with [UrbanCode Deploy](t_integration_UCD.md#) and other external tools, such as [Jenkins](t_integration_Jenkins.md#). The integration process is required. No report data is available until the integration process is complete. Authenticating users to access reports is not required. However; until users are authenticated only the administrator user has access.

6.  **Authenticate users**

    After the installation is complete, you can [authenticate users](t_admin_authentication.md#). The integration process is required. No report data is available until the integration process is complete. Authenticating users to access reports is not required. However; until users are authenticated only the administrator user has access.


-   **[Installation roadmap](../topics/c_install_se_roadmap.md)**  
The installation roadmap is a description of the high-level steps for installing UrbanCode Velocity.
-   **[System requirements](../topics/c_install_se_requirements.md)**  
Installation requirements for all installation scenarios.
-   **[Installing UrbanCode Velocity with Docker Compose](../topics/t_install_se_docker.md)**  
Instructions for installing UrbanCode Velocity into the Docker Compose container orchestrator.
-   **[Installing into a Kubernetes cluster](../topics/t_install_se_kubernetes.md)**  

-   **[Uninstalling the server](../topics/t_install_se_remove_ucv.md)**  
You can uninstall UrbanCode Velocity by stopping the server and removing the product containers.

**Parent topic:** [Installation roadmap](../topics/c_install_se_roadmap.md)

