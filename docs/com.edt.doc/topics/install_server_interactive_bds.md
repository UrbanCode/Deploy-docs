# Installing the blueprint design server in interactive mode

In interactive mode, you install the blueprint design server by typing configuration information in a command-line program. This installation includes the cloud discovery service.

-   Ensure that your account has the required permissions:
    -   If you install the blueprint design server on a Linux™ operating system, root access is required. The operating system must have the most recent package updates. For more information, see [Installing and Managing Software](https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/7/html/System_Administrators_Guide/part-Installing_and_Managing_Software.html) in the Red Hat Enterprise Linux customer portal.
    -   If you install the blueprint design server on a Windows™ operating system, your account must be a member of the Administrators group.
-   Make sure that your system meets the system requirements. See [System requirements and performance considerations](sysRequire.md).
-   Make sure that your networks and firewalls allow communication on the required ports. See [Firewall and communication configuration](agent_firewalls.md).
-   Make sure that you have a license server with available HCL UrbanCode Deploy licenses.
-   Install or extend an engine. See [Installing the engine](install_engine.md).
-   Install or upgrade the HCL UrbanCode Deploy server.
-   Create an authorization token on the HCL UrbanCode Deploy server. You must have this token to retrieve information about components from the server.
-   Configure a database for the blueprint design server. See [Blueprint design server database configuration](install_database_bds_ov.md).
-   If you are using a database other than Apache Derby or PostgreSQL, either note the location of the JDBC JAR file for the database or place the file in the installation\_directory/ibm-ucd-patterns-install/web-install/media/server/opt/tomcat/lib folder.
-   If you install the blueprint designer on a Linux operating system, install the following prerequisite packages:

    -   `gcc`
    -   `python-devel`
    -   `openssl-devel`
    -   `libffi-devel`
    On a Red Hat Enterprise Linux system, the command to install these packages might resemble the following code:

    ```
    yum install -y gcc python-devel openssl-devel libffi-devel
    ```

-   If you install the blueprint designer on a Windows system, install Python 2.7.9 or a higher 2.x version. Version 3 and later are not supported. You can install Python yourself, or the installation program will install a compatible version.
-   Ensure that there is no limit on the maximum memory size and virtual memory size. For example, on most Linux systems, you can run the `ulimit -m` and `ulimit -v` commands and ensure that both return the value `unlimited`. To find out how to remove the limit on the maximum memory size and virtual memory size, see the documentation for the operating system.

When you install the blueprint design server, you also install its supporting services: the cloud discovery service and a Git server. The cloud discovery service provides information about your configured clouds to the blueprint designer. You can store the blueprints and configuration files that you create for the blueprint designer in the local Git server.

1.   Download and extract the installation files for the blueprint design server. These files are available for download from the IBM® Passport Advantage® website. See the [IBM UrbanCode Deploy download document](https://www.ibm.com/software/passportadvantage/pao_customer.html). 
2.   From the command line, run the installation program. On Windows, you must use the command line instead of the Windows PowerShell.
    -   On Linux, change to the installation\_directory/ibm-ucd-patterns-install/web-install/ folder, and run the install.sh file.
    -   On Windows, change to the installation\_directory folder, and run the install.bat file.
3.   At the prompt **If you do not have Python 2 installed, press 'y' and Python 2.7.9 will be installed on this machine**, press y if Python is installed or if you want to install Python automatically. Press n to close the installer and install Python on your own. 
4.   Read the license agreements for the software package. Press the Space bar to show one page at a time, or press F to show the entire license text. 
5.   If you agree to the terms of all of the license agreements, press Y, and then press Enter. 
6.   Specify the following information as the installation program prompts you. You can accept the default values \(displayed within brackets\) by pressing Enter. If two options are given, such as `[Y/n]`, the uppercase option is the default value.
    -   ****Specify the directory where the blueprint design server for UrbanCode Deploy should be installed.****

        Specify the directory to install the blueprint design server in. The default installation directory is /opt/ibm-ucd-patterns on Linux™ and C:\\Program Files\\ibm-ucd-patterns on Windows™.

    -   ****The specified directory does not exist. Do you want to create it?****

        Press `Y` to create the installation directory.

    -   ****Enter the public IP address or host name of this system.****

        Specify the public IP address or host name that other systems, such as the HCL® UrbanCode™ Deploy server, use to access this system. In most cases, specify the host name of the computer that hosts the server, such as `designserver.example.com`.

    -   ****Do you want the blueprint design server to always use secure connections using SSL?****

        Press Y to use secure connections to the blueprint design server. If you select this option, you must configure a certificate for the blueprint design server; see [Configuring SSL security on Apache Tomcat for the blueprint design server](ssl_config_server_bds.md).

    -   ****Enter the port on which the blueprint design server should listen for secure HTTPS requests.****

        Specify the HTTPS port for the blueprint design server. The default value is `8443`. If you are installing the HCL® UrbanCode™ Deploy server and the blueprint design server on the same computer, be sure to use a different port for each server.

    -   ****Enter the port to which the blueprint design server should redirect unsecured HTTP requests.****

        Specify the HTTP port for the blueprint design server. The default value is `8080`.If you are installing the HCL® UrbanCode™ Deploy server and the blueprint design server on the same computer, be sure to use a different port for each server.

    -   **Create database schema?**

        In most cases, press Y to create new schema definitions in the database. However, if you have a pre-populated database, press N.

    -   ****Enter the database type to use.****

        Specify the type of database to use. For production systems, specify mysql, mariadb, db2, oracle, sqlserver, or postgres. For evaluation systems, you can use one of these databases, or you can specify derby to have the installer create a database for you.

        **Note:** Derby is not appropriate for production blueprint design servers.

        Specify the following information for the database connection:

        -   ****Enter the database driver.****

            Specify the class name of the driver, such as `com.mysql.jdbc.Driver`. This field is required only if you are not using a Derby database.

        -   ****Enter the database connection string.****

            Specify the complete connection string for the database. For example, if you use a MySQL database, the connection string resembles the following code: `jdbc:mysql://hostname:3306/ibm_ucdp` , where hostname is the host name or IP address of the database server.

            If you are using the MySQL database on an engine, specify `jdbc:mysql://engine.example.org:3306/ibm_ucdp` , where engine.example.org is the host name or IP address of the engine.

        -   ****Enter the database username.****

            Specify the user name for the database. The default user name is `ibm_ucdp`. If you are connecting to a production database, specify the user name for an existing account on the database. If you are creating a Derby database, specify a new user name for the database.

        -   ****Enter the database password.****

            Specify the password for the database. The default password is `password`. If you are connecting to a production database, specify the password for the database account. If you are creating a Derby database, specify a new password for the database account.

        -   **Enter the path to the database library jar file to copy into your installation.**

            If you are using a production database, specify the location and file name of the database JDBC JAR file. For example, on Linux™ the path and file name might look like this string: /root/mysql-connector-java-5.1.27-bin.jar. On Windows™, the path and file might look like this string: C:\\tmp\\mysql-connector-java-5.1.27-bin.jar

    -   ****Enter the URI for the IBM UrbanCode Deploy server.****

        Specify the URL for the server, including the port. The default port is 8443, for example: `https://deployserver.example.org:8443`.

        **Note:** Do not include a slash at the end of this URL.

        If you do not want to connect, leave this field blank.

    -   ****Enter the authentication token to access the UrbanCode Deploy server.****

        Specify the authentication token from the HCL® UrbanCode™ Deploy server. If you are not connecting, leave this field blank.

7.   If you installed the blueprint design server on a Windows operating system, register the blueprint designer as a Windows service. 
    1.   As an administrator, run the following command: 

        ```
        C:\\installation\_directory\\bin\\service\\service.cmd install ucdp
        ```

        In this code, the installation\_directory is the directory that you installed the blueprint design server in. By default, the command resembles the following code:

        ```
        C:\\Progra~1\\ibm-ucd-patterns\\bin\\service\\service.cmd install ucdp
        ```

    2.   Specify the following information as the installation program prompts you. You can accept the default values \(displayed within brackets\) by pressing Enter. If two options are given, such as `[Y/n]`, the uppercase option is the default value.
        -   **Enter the user account name including domain path to run the service as.**

            Specify the user account with which to run the service, including the domain path. Prefix local accounts with a period, such as .\\localsystem.

        -   **Do you want to start the ucdp service automatically?**

            Press Y to start the server automatically. Otherwise, you can start and stop the server manually. See [Starting the blueprint designer, cloud discovery service, and engine](start_patterns.md#).

            **Note:** The ucdp service starts only the blueprint designer. You must manually start the cloud discovery service.

    3.   Start the service by running the following command: 

        ```
        net start ucdp
        ```

8.   Configure the cloud discovery service. While you can use the default settings for the cloud discovery service, you can also provide information about the specific regions, flavors, and images that you use with some clouds. If you want to customize the cloud discovery service, you can customize it now or when you connect to a cloud. See [Setting up images, regions, and flavors for the cloud discovery service and engine](../../com.udeploy.doc/topics/cds_configure.md).
9.   Start the cloud discovery service: 
    -   On Linux systems that manage services with the systemd system manager, use the systemctl command:

        ```
        systemctl start ibm-cloud-discovery.service
        ```

    -   On Linux systems that do not manage services with the systemd system, run the following command:

        ```
        cloud-discovery-service &
        ```

    -   On Windows, run the following command:

        ```
        C:\python\_installation\_directory\Scripts\cloud-discovery-service.exe
        ```

        Use the location where Python is installed for `python\_installation\_directory`. The default installation directory is C:\\Python27. By default, the command looks like this code:

        ```
        C:\Python27\Scripts\cloud-discovery-service.exe
        ```

10.  If you installed the blueprint design server on the same computer that you installed the engine, restart the Heat services and Keystone, if applicable. See [Starting the blueprint designer, cloud discovery service, and engine](start_patterns.md#).
11.  Start the blueprint design server: 
    -   On Linux, run the following command:

        ```
        server\_installation\_directory/bin/server start
        ```

        Use the location of the blueprint design server installation for `server\_installation\_directory`. The default installation directory is /opt/ibm-ucd-patterns. By default, the command looks like the following code:

        ```
        /opt/ibm-ucd-patterns/bin/server start
        ```

    -   On Windows, run the following command:

        ```
        C:\server\_installation\_directory\bin\start_server
        ```

        Use the location of the blueprint design server installation for `server\_installation\_directory`. The default installation directory is C:\\Program Files\\ibm-ucd-patterns. By default, the command looks like the following code:

        ```
        "C:\Program Files\ibm-ucd-patterns\bin\start_server"
        ```


You can access the blueprint design server by opening the following URL in a web browser: `https://hostname:port/landscaper` , where `hostname` is the host name of the blueprint design server and `port` is the HTTP port that you specified when you installed the blueprint design server. The default administrator user name is `ucdpadmin`, and the default password is `ucdpadmin` .

After you install the blueprint design server, you can configure it. You might complete these tasks:

-   Configure an authentication realm to import users to the blueprint design server. See [Creating authentication realms for the blueprint designer](../../com.udeploy.admin.doc/topics/security_realms_create.md#).
-   Connect to a cloud. See [Connecting to clouds through the blueprint designer](security_cloud_connection.md).
-   Connect the blueprint design server to the HCL UrbanCode Deploy. See [Connecting the blueprint design server to the server](../../com.udeploy.doc/topics/ucdp_integrate.md#).
-   Configure the Git repository that contains the blueprints. You can connect to an external Git repository or use the Git server that included with the blueprint design server. See [Changing the local Git server password](../../com.udeploy.doc/topics/blueprint_gitblit.md#).

**Parent topic:** [Installing the blueprint design server](../../com.edt.doc/topics/install_server_bds.md)

