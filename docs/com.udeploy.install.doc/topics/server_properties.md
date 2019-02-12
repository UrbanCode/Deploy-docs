# Server installation properties

The server properties in the installed.properties file control details about the server, such as what ports it uses.

Some of these properties are listed in a table in [Installing the server in silent mode](server_install_silent.md). Some properties can be changed after the server is installed and others cannot. After the server starts for the first time, the server adds other properties to the installed.properties file. Some of these additional properties can be changed and others cannot.

By default, this file is in the folder /opt/ucd/server/conf/server.

For example, the server adds the property server.host, which specifies the IP addresses on which the server listens for JMS connections. In most cases, the server sets this property to the value `0.0.0.0`, which means that the server listens for JMS connections on all IP addresses that it has available. You can specify a specific IP address in this property to limit the IP addresses that the server listens on.

**Parent topic:** [Installing the server](../../com.udeploy.install.doc/topics/serverInstall.md)

