# Installing an engine in interactive mode

In interactive mode, you install the Heat orchestration engine for the blueprint design server by typing configuration information in a command-line program.

Before installing the engine, you must complete the steps in the "Before you begin" section of [Installing a standalone engine](install_engine_standalone.md).

In interactive mode, you install the Heat orchestration engine for the blueprint design server by typing configuration information in a command-line program. If you already use a Keystone server, you can use it as your identity service for the blueprint design server. If you do not use a Keystone server, you can install one with the engine.

1.  To install an engine in interactive mode:
2.   Download and extract the installation files for the engine. These files are available for download from the IBM® Passport Advantage® website. See the [IBM UrbanCode Deploy download document](https://www.ibm.com/software/passportadvantage/pao_customer.html). 
3.   Change to the ibm-ucd-patterns-install/engine-install/ directory. 
4.  From the command line, run ./install.sh to start the installation program.
5.   The first question the installer asks is, **Have you satisfied these dependencies?** If you configured the system with the prerequisites for the engine, press Y, and then press Enter. 
6.   Read the license agreements for the software package. Press the Space bar to show one page at a time, or press F to show the entire license text. 
7.   If you agree to the terms of all of the license agreements, press Y, and then press Enter. 
8.  Specify the following information as the installation program prompts you.You can accept the default values \(displayed within brackets\) by pressing Enter. If two options are given, such as `[Y/n]`, the capitalized option is the default value.
    -   ****Enter the public host name that clients use to access this Heat orchestration engine.****

        Specify the public IP address or host name that other systems, such as the blueprint design server, use to access this system.

    -   ****Enter the binding address for the Heat orchestration engine. Accept the default value to listen to all addresses that are available to the system.****

        Specify the IP address that the engine listens for requests on. Specify `0.0.0.0` to listen on all addresses that are available to the system.

    -   ****Enter the OpenStack Identity endpoint URL to use for authorization for this Heat orchestration engine. Accept the default value to install Keystone.****

        Specify the complete URL of the Keystone server that you are using for your identity service, such as `http://cloud.example.com:5000/v3`. Do not include a trailing slash. If you do not have a Keystone server, specify the default location to install and configure one. The default location is http://public\_host\_name:5000/v3.

    -   ****Do you want to start and enable the required OpenStack services for this Heat engine?****

        Specify Y to start the engine services automatically after they are installed.

9.   After the installation program is complete, add an automated task to remove expired keys from the database. Having too many expired keys in the database can degrade system performance. For example, the following command creates an automated task in the Linux™ program cron to remove old keys. This command must be written on a single line.

    ```
     (crontab -l -u keystone 2>&1 | grep -q token_flush) 
      || echo '@hourly /usr/bin/keystone-manage token_flush 
      >/var/log/keystone/keystone-tokenflush.log 2>&1' 
      >> /var/spool/cron/keystone
    ```


The installation program installs the engine.

If you did not start the engine services during installation, start them. See [Starting the blueprint designer, cloud discovery service, and engine](start_patterns.md#).

The Keystone server's default administrative tenant user name is `admin` and the default password is `openstack1`. The authorization token is listed in the /etc/keystone/keystone.conf and /root/keystonerc file.

The installation process automatically started the required backend services for the engine. If you stop the backend services while the OpenStack services for the Heat engine are running, the OpenStack services for the Heat engine fail. If you did not start the engine, then you can stop these services. For example, the following commands stop the backend services in RHEL 7:

```
systemctl stop rabbitmq-server.service
```

```
systemctl stop mariadb.service
```

```
systemctl stop openstack-keystone.service
```

To interact with the Heat engine, you use its provided credentials in your user directory. The `clientrc` file that contains the Heat engine credentials also contains the credentials for the Keystone identity service. Run the following commands:

```
source ~/clientrc
```

```
openstack endpoint list
```

```
heat stack-list
```

You can also interact with only the Keystone identity service by using its prepared credentials files in your user directory. Run this command to load the credentials file:

```
source ~/keystonerc
```

For version 6.2.2 and later, run the following command:

```
openstack endpoint list
```

Because the keystone command line interface is deprecated, run commands against the OpenStack client instead. See the OpenStack documentation.

After you start the OpenStack services for the Heat engine, you can access the REST API at the following URL: `http://host\_name:8004`.

