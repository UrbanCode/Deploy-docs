# Installing the blueprint design server in silent mode

In silent mode, you install the blueprint design server by specifying configuration information in command-line arguments. This installation includes the cloud discovery service.

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

1.   Download and extract the installation files for the blueprint design server. These files are available for download from the IBM® Passport Advantage® website. See the [IBM UrbanCode Deploy download document](https://www.ibm.com/software/passportadvantage/pao_customer.html). 
2.   Read the license agreement. On Linux, it is in this folder: installation\_directory/ibm-ucd-patterns-install/web-install/media/server/licenses/. On Windows, it is in this folder: installation\_directory\\media\\server\\licenses 
3.   From the command line, change the working directory. On Linux, change to the installation\_directory/ibm-ucd-patterns-install/web-install/ folder, and on Windows, change to the installation\_directory folder.
4.   From the command line, run the installation command. This command must be on a single line.

    -   On Linux, run the following command:

        ```
        ./install.sh -l options
        ```

    -   On Windows, run the following command:

        ```
        ./install.bat -l options
        ```

    **Note:** The `-l` option in this command indicates that you read and accepted the license agreement.

    For `options`, include all the following arguments:

    |Argument|Default value|Required or optional|Description|
    |--------|-------------|--------------------|-----------|
    |`-f install\_directory`|On Linux, /opt/ibm-ucd-patterns, and on Windows, C:\\Program Files\\ibm-ucd-patterns|Optional|Specify the directory to install the blueprint design server in.|
    |`-i server\_hostname`|The host name of the current system|Required|Specify the public IP address or host name that other systems, such as the HCL UrbanCode Deploy server, use to access this system.|
    |`-o ucd\_server`|`https://localhost:8443`|Optional for Linux, not applicable for Windows|Specify the full URL of the HCL UrbanCode Deploy server, including the port number. **Note:** Do not include a slash at the end of this URL.

|
    |`-t token`|None|Optional for Linux, not applicable for Windows|Specify the authorization token for the connection to HCL UrbanCode Deploy.|
    |`-e cloud\_discovery`|`http://localhost:7575`|Required|Specify the URI to the cloud discovery service, which is URL of the blueprint design server with the default port 7575, such as `http://blueprint_design_server.myserver.com:7575` .|
    |`-d db\_type`|`derby`|Required|Specify the type of database to use. For production systems, specify `mysql`, `mariadb`, `DB2`, `oracle`, or `sqlserver`. For evaluation systems, you can also specify `derby` to have the installer create a database for you.|
    |`-a db\_url`|`jdbc:mysql://localhost:3306/ibm_ucdp`|Required if you are not using a Derby database|Specify the complete connection string for the database. For example, if you use a MySQL database, the connection string resembles the following code: `jdbc:mysql://hostname:3306/ibm_ucdp` , where hostname is the host name or IP address of the database server. If you are using the MySQL database on an engine, specify `jdbc:mysql://engine.example.org:3306/ibm_ucdp` , where engine.example.org is the host name or IP address of the engine.|
    |`-v db\_user`|`ibm_ucdp`|Required if you are not using a Derby database|Specify the user name for the database.|
    |`-q db\_password`|`password`|Required if you are not using a Derby database|Specify the password for the database.|
    |`-m database\_driver`|`com.mysql.jdbc.Driver`|Required if you are not using a Derby database|If you are using a MySQL, MariaDB, DB2®, Oracle, or Microsoft™ SQL Server database, specify the class name of the JDBC driver. If you are using Derby, omit this argument.|
    |`-n argument\_value`|`N`|Optional|To escape the database schema creation, set the argument value to `N`. The default value is `Y`.|

    For example, the following Linux command installs the blueprint design server, installs a Derby database for the blueprint design server to use, and connects to the server:

    ```
    ./install.sh -l 
    -i designserver.example.com
    -o https://deployserver.example.org:8443 
    -t ABCDE12345 
    -e http://engine.myserver.com:7575 
    -d derby 
    ```

    The following Windows command installs the blueprint design server and installs a Derby database for the blueprint design server to use:

    ```
    ./install.bat -l 
    -i designserver.example.com
    -e http://engine.myserver.com:7575 
    -d derby
    ```

     These examples are split onto separate lines for clarity, but the command must be entered on a single line. To use another database, you must specify the information for the existing database. Be sure to place the JAR file for the database driver in the installation directory. The following example for Linux uses a MySQL database:

    ```
    ./install.sh -l 
    -i designserver.example.com
    -o https://deployserver.example.org:8443 
    -t ABCDE12345 
    -e http://engine.myserver.com:7575 
    -d mysql 
    -a jdbc:mysql://localhost:3306/ibm_ucdp
    -v ibm_ucdp
    -q password
    -m com.mysql.jdbc.Driver
    -n N
    ```

    If you omit a required argument, the installation program prompts for the value, which means that the silent installation becomes interactive.

5.   If you installed the blueprint design server on a Windows operating system, register the blueprint designer as a Windows service. 
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

6.   Configure the cloud discovery service. While you can use the default settings for the cloud discovery service, you can also provide information about the specific regions, flavors, and images that you use with some clouds. If you want to customize the cloud discovery service, you can customize it now or when you connect to a cloud. See [Setting up images, regions, and flavors for the cloud discovery service and engine](../../com.udeploy.doc/topics/cds_configure.md).
7.   Start the cloud discovery service: 
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

8.   If you installed the blueprint design server on the same computer that you installed the engine, restart the Heat services and Keystone, if applicable. See [Starting the blueprint designer, cloud discovery service, and engine](start_patterns.md#).
9.   Start the blueprint design server: 
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

