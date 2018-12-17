# Upgrading engines that you extended

To upgrade a Heat orchestration engine that you extended, rerun the script that extends the engine.

-   Root access is required for installation.
-   The operating system must be configured with required packages and dependencies before you install the engine. The system might need network access to install these packages. Make sure that the system is connected to a package manager, such as a Yum server.
-   If the `akonadi` package is installed, remove it:

    ```
    yum remove -y akonadi
    ```

-   Determine whether the program `qpid` is installed on the system.
    -   On RHEL version 7, run the following command:

        ```
        systemctl status qpidd.service
        ```

-   If the program `qpid` is running on the system, stop its service.
    -   On RHEL version 7, run the following command:

        ```
        systemctl stop qpidd.service
        ```


These steps are for upgrading Heat orchestration engines that you extended as described in [Extending an existing OpenStack engine](extending_an_engine_for_openstack.md) or for upgrading Heat engines that you installed with HCL® UrbanCode™ Deploy version 6.2.1.1 or later. For other Heat engines, use the instructions in [Upgrading engines that you installed with HCL UrbanCode Deploy](upgrade_engine_ucdp.md).

1.   Check the current version of the custom types in the engine. You need to know the current version of the types so you will know if the upgrade was successful. To check the current version, log in to the system that hosts the engine and run the following command:

    ```
    pip list | grep ibm-cloud-ext
    ```

    Then, find the version of the `ibm-cloud-ext` package in the output of the command. For example, assume that the output looks like the following code:

    ```
    ibm-cloud-ext (6.2.1.dev70)
    ```

    In this example, the version of the custom types is `(6.2.1.dev70)`.

2.   Download and extract the installation files for the engine. These files are available for download from the IBM® Passport Advantage® website. See the [IBM UrbanCode Deploy download document](https://www.ibm.com/software/passportadvantage/pao_customer.html). 
3.   Change to the ibm-ucd-patterns-install/engine-install/ directory. 
4.   From the command line, run the ./extend-ucd-existing-engine.sh command to install the HCL UrbanCode Deploy plug-in. 
5.   The installer asks if you have satisfied the dependencies. If you configured the system with the prerequisites for the engine, press `Y`. 
6.   Read the license agreements for the software package. Press Space to show one page at a time, or press `F` to show the entire license. 
7.   If you agree to the terms of all of the license agreements, press `Y`, and then press Enter. 
8.   Restart the engine and the Heat API. See the documentation for your cloud system.
9.   Run the following command and verify that the version of the `ibm-cloud-ext` package has been updated: 

    ```
    pip list | grep ibm-cloud-ext
    ```


The engine is updated.

**Parent topic:** [Upgrading engines](../../com.ibm.edt.doc/topics/upgrade_engine.md)

