# Installing an engine in silent mode

In silent mode, you install the Heat orchestration engine for the blueprint design server by specifying configuration information in command-line arguments.

Before installing the engine, you must complete the steps in the "Before you begin" section of [Installing a standalone engine](install_engine_standalone.md).

In interactive mode, you install the Heat orchestration engine for the blueprint design server by typing configuration information in a command-line program. If you already use a Keystone server, you can use it as your identity service for the blueprint design server. If you do not use a Keystone server, you can install one with the engine.

1.   Download and extract the installation files for the engine. These files are available for download from the IBM® Passport Advantage® website. See the [IBM UrbanCode Deploy download document](https://www.ibm.com/software/passportadvantage/pao_customer.html). 
2.   Change to the ibm-ucd-patterns-install/engine-install/ directory. 
3.  Read the license agreement, which is in the following folder: ibm-ucd-patterns-install/engine-install/resources/. 
4.  From the command line, run the following command.This command must be on a single line.

    **Note:** The `-l` option indicates that you have read and accepted the license agreement.

    ```
    ./install.sh
      -l options
    ```

    For `options`, include the following arguments:

    |Argument|Required or optional|Description|
    |--------|--------------------|-----------|
    |`-a openstack\_URL`|Required|Specify the complete URL of the Keystone server that you are using for your identity service, such as `http://cloud.example.com:5000/v3`. Do not include a trailing slash. If you do not have a Keystone server, specify the default URL to use the Keystone server instance that is installed when you install the engine. In version 6.2.2 and later, the default URL is http://public\_host\_name:5000/v3.|
    |`-b bind\_address`|Required|Specify the IP address that the engine listens for requests on. Specify `0.0.0.0` to listen on all addresses that are available to the system.|
    |`-i engine\_hostname`|Required|Specify the public IP address or host name that other systems, such as the blueprint design server, use to access this system.|
    |`-s Yes or No`|Required|Specify Yes to start the required OpenStack Heat and Keystone services or No to not start the services.|

    For example:

    ```
    ./ibm-ucd-patterns-install/engine-install/install.sh -l
    -a http://cloud.example.com:5000/v2.0
    -i engine.example.com
    -b 0.0.0.0
    -s Yes
    ```

    These examples are split onto separate lines for clarity, but the command must be entered on a single line. If you omit a required argument, the installation program prompts for the value, which means that the silent installation becomes interactive.

5.   After the installation program is complete, add an automated task to remove expired keys from the database. Having too many expired keys in the database can degrade system performance. For example, the following command creates an automated task in the Linux™ program cron to remove old keys. This command must be written on a single line.

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

**Parent topic:** [Installing a standalone engine](../../com.edt.doc/topics/install_engine_standalone.md)

