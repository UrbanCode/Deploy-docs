# Installing a standalone engine

To deploy environments to non-OpenStack clouds, such as Amazon Web Services, SoftLayer, VMware, Google Cloud, and Microsoft Azure, you install the blueprint design server and Heat engine through IBM UrbanCode Deploy. You can install the engine in interactive mode or in silent mode.

-   Do not install an engine with these steps to connect to an OpenStack or OpenStack-based cloud. Instead, to extend an existing engine on the OpenStack-based cloud, see [Extending an existing OpenStack engine](extending_an_engine_for_openstack.md).
-   The upgrade-standalone-ucd-heat-engine.sh script can only be used with the provided heat engine that comes with HCL® UrbanCode™ Deploy blueprint designer. It installs both the HCL UrbanCode Deploy plug-in and the ibm-cloud-ext package.

Before you install the engine, ensure that you do the following steps:

1.  You must install the engine on a host that runs a specific version of Red Hat Enterprise Linux™ \(RHEL\).

    -   In version 6.2.2 and later, the HCL UrbanCode Deploy installer can install engines for the blueprint design server only on RHEL version 7. No other operating system is supported, including RHEL version 6 or earlier.
    To use a different operating system, you can install an OpenStack Heat engine manually on that operating system and then extend that engine for use with the blueprint design server; see [Extending an existing OpenStack engine](extending_an_engine_for_openstack.md).

2.  The engine installer installs only a specific version of the OpenStack Heat orchestration engine.

    -   In version 6.2.2 and later, the installer installs only OpenStack Kilo engines.
    To use a different version of the OpenStack Heat orchestration engine, you can extend an existing engine of that version; see [Extending an existing OpenStack engine](extending_an_engine_for_openstack.md). You can extend OpenStack Icehouse, Juno, Kilo, Liberty, and Mitaka engines for use with the blueprint design server.

3.  The operating system must have the most recent package updates. For more information, see [Installing and Managing Software](https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/7/html/System_Administrators_Guide/part-Installing_and_Managing_Software.html) in the Red Hat Enterprise Linux customer portal.
4.  Ensure that there is no limit on the maximum memory size and virtual memory size. For example, on most Linux systems, you can run the `ulimit -m` and `ulimit -v` commands and ensure that both return the value `unlimited`. To find out how to remove the limit on the maximum memory size and virtual memory size, see the documentation for the operating system.
5.  Root access is required for installation.
6.  The engine installs a MariaDB database automatically. You must install the engine on a system on which MariaDB is not installed. If the database is already installed on the system, the engine installation fails.
7.  The operating system must be configured with required packages and dependencies before you install the engine. The system might need network access to install these packages. Make sure that the system is connected to a package manager, such as a Yum server.
8.  Make sure that your system meets the system requirements. See [System requirements and performance considerations](sysRequire.md).
9.  Make sure that your networks and firewalls allow communication on the required ports. See [Firewall and communication configuration](agent_firewalls.md).
10. Install the following packages:

    -   `gcc`
    -   `genisoimage`
    -   `libffi-devel`
    -   `python-devel`
    -   `openssl-devel`
    For example, the command to install these packages might resemble the following code:

    ```
    yum install -y gcc genisoimage libffi-devel python-devel openssl-devel
    ```

11. Enable the optional "rhel-7-server-optional-rpms" repository.
    -   On RHEL systems that use the Red Hat Network subscription-based package manager, use the following command:

        ```
        subscription-manager repos --enable=rhel-7-server-optional-rpms
        ```

    -   On virtual machines that are hosted on Amazon Web Services, run the following command:

        ```
        yum-config-manager --enable rhui-REGION-rhel-server-optional
        ```

12. Determine whether the `akonadi` package is installed on the system.

    ```
    rpm -ql akonadi
    ```

13. If the `akonadi` package is installed, remove it:

    ```
    yum remove -y akonadi
    ```

14. Determine whether the program `qpid` is installed on the system.
    -   On RHEL version 7, run the following command:

        ```
        systemctl status qpidd.service
        ```

15. If the program `qpid` is running on the system, stop its service.
    -   On RHEL version 7, run the following command:

        ```
        systemctl stop qpidd.service
        ```

16. Gather the URL and account information for the OpenStack Keystone service, if available.Rather than having its own list of users, the blueprint design server imports accounts from authentication realms, including OpenStack Keystone services and LDAP servers. This Keystone service is required regardless of the type of cloud you are using. If you do not have a Keystone server, you can install one that uses Identity API v3 during the engine installation.

Choose to install the engine in interactive mode or in silent mode:

-   **[Installing an engine in interactive mode](../../com.ibm.edt.doc/topics/install_engine_interactive.md)**  
In interactive mode, you install the Heat orchestration engine for the blueprint design server by typing configuration information in a command-line program.
-   **[Installing an engine in silent mode](../../com.ibm.edt.doc/topics/install_engine_silent.md)**  
In silent mode, you install the Heat orchestration engine for the blueprint design server by specifying configuration information in command-line arguments.

**Parent topic:** [Installing the engine](../../com.ibm.edt.doc/topics/install_engine.md)

