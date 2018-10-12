# System requirements {#c_install_se_requirements .concept}

Installation requirements for all installation scenarios.

You can install UrbanCode® Velocity into environments that support Docker Compose or Kubernetes, including the following environments:

-   Windows
-   Linux
-   MacOS
-   IBM Cloud Private
-   IBM Cloud services
-   Amazon Web Services
-   Google

The tools that are required for all installation scenarios are described here. Make sure that your user ID meets the requirements for installing and configuring the product. The user ID must be able to make changes to the host environment. In addition, you need user accounts for the tools specific to your installation scenario.

The tools required by all installation scenarios include the following items:

-   Docker
-   IBM UrbanCode™ Deploy Version 6.2.3 and later. Although not strictly required, many UrbanCode Velocity features assume integration with UrbanCode Deploy. It doesn't matter which product you install first.

    If you are using an UrbanCode Deploy version prior to V6.2.5, you must install the patch located at the following website: [http://public.dhe.ibm.com/software/products/UrbanCode/plugins/ucsync/patches/ibmucd/](http://public.dhe.ibm.com/software/products/UrbanCode/plugins/ucsync/patches/ibmucd/). Select from the index the appropriate version that is installed on your computer.

    UrbanCode Velocity can connect to an UrbanCode Deploy server on the same network. If you install UrbanCode Velocity with Kubernetes, the Kubernetes cluster must be on the same network as the UrbanCode Deploy server.

-   Git and a GitHub account.

**Note:** 

The commands used during installation retrieve files and container images from remote locations. If you are unable to access the internet during installation, the install images will need to have been previously downloaded and placed in a docker repository that the installation commands have accessed.

You can dynamically generate a system requirements report using the [Software Product Compatibility Reports \(SPCR\)](https://www.ibm.com/software/reports/compatibility/clarity/index.html) tool.

**Parent topic:** [Installation roadmap](../topics/c_install_se_roadmap.md)

