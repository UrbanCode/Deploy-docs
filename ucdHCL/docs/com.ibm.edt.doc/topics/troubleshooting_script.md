# Engine troubleshooting script

If you have a problem with the HCL® UrbanCode™ Deploy engine, run the troubleshooting script to provide IBM® Software Support and developers information about the status of your engine. Consider running this script and having the results available before you call IBM Software Support. This script applies to OpenStack Heat orchestration engines that are at the Juno or Kilo level.

If the default installation location is used, the engine-tools.sh script location is as follows: /engine\_install/resources/tools/engine-tools.sh, where engine\_install is the installation directory. Use the following options with the engine-tools.sh command to gather troubleshooting data about your engine. You can change to the directory or enter the path as part of the command. The options can be used in combination.

If a high availability installation is used, you can use the ha-engine-tools.sh script instead. If the default installation location is used, script location is as follows: /engine\_install/resources/tools/ha/ha-engine-tools.sh, where engine\_install is the installation directory. Except for the `-r` option, the following options can be used with the ha-engine-tools.sh command.

|Option|Argument|Description|
|------|--------|-----------|
|`-a`|None|Store the configuration and log files in a .tar file. Use this option with other options such as `-c`, `-e`, `-i`, `-l`, and `-p`. For example, enter `./engine-tools.sh -c -a`.|
|`-c`|None|Collect files and logs for HCL UrbanCode Deploy engine services.|
|`-d`| -   `on`
-   `off`
-   `status`

 |Modify or view the heat debug setting. Specify `[ on|off|status ].` For example, enter `./engine-tools.sh -d off -s restart`.|
|`-e`|None|Create a backup of the IBM UrbanCode Deploy engine plug-in by copying the contents of the /usr/lib directory|
|`-i`| -   `system`
-   `openstack`
-   `database`
-   `all`

 |Collect system, OpenStack, or database information, such as host names, ports, process limits, and configuration details. Specify `[ system|openstack|database|all ]`.|
|-l|None|Collect heat engine and Keystone logs.|
|`-p`|None|Check the performance of the heat engine and redirect the performance output to the heat\_performance.\#.out file. Before you run this command, you must source the clientrc file that is located in the /root/ directory.|
|`-r`**Restriction:** This option is not available with the ha-engine-tools.sh script.

| -   `status`
-   `restart`
-   `stop`
-   `start`

 |Report on, restart, stop, or start all the required services such as MySQL, MariaDB, and RabbitMQ. Specify `[ status|restart|stop|start ]`. For example, enter `./engine_tools.sh -r status`.|
|`-s`| -   `status`
-   `restart`
-   `stop`
-   `start`

 |Check the status of the OpenStack services \(engine and Keystone\), or restart, stop, or start the services. Specify `[ status|restart|stop|start ]`. For example, enter `./engine_tools.sh -s restart`.|
|`-t`|None|Tail the heat engine log and view real-time log values.|

**Parent topic:** [Troubleshooting engines](../../com.ibm.edt.doc/topics/trouble_engines.md)

