# Authenticating for REST commands

The way that you authenticate to run REST commands depends on how the server is set up and the tool that you are using to run the commands.

**Note:** Using REST commands requires the same permissions as using the web interface. For information about permissions, see [Roles and permissions](../../com.udeploy.admin.doc/topics/security_roles.md).

## Authenticating with a user name and password

The simplest way to authenticate for REST commands is to use a user name and password. For example, if you are using the `curl` program, you can specify the user name and password in the command, as in the following code:

```
curl -k -u jsmith:passwd
  https://myserver.example.com:8443/cli/application/info
  ?application=JPetStore
```

## Authenticating in scripts and programs

Many programming and scripting languages can call REST commands.

The following example is a Python script that authenticates by adding the password to the request header.

```
#!/usr/bin/env python

import urllib2
import json
import base64
import sys

if not len(sys.argv) == 3:
  print 'usage: script <username> <password>'
  exit(1)

username = sys.argv[1]
password = sys.argv[2]

epass = base64.b64encode(username + ':' + password)
print 'base64 encoded: ' + epass
baseUrl = 'ucdeploy.example.org:8443'

url = 'https://' + baseUrl + '/cli/application/info' + '?application=JPetStore'

opener = urllib2.build_opener(urllib2.HTTPHandler)
req = urllib2.Request(url)
req.add_header('Authorization', 'Basic '+epass)
req.get_method = lambda: 'GET'

resp = opener.open(req)
print resp.read()
```

## Authenticating in a Groovy script

For an example of authenticating in a Groovy script, see the following repository: [https://github.com/IBM-UrbanCode/groovy-sample-scripts-UCD](https://github.com/IBM-UrbanCode/groovy-sample-scripts-UCD)

## Importing the server certificate

The default server certificate is unsigned. Some tools do not connect to servers with unsigned certificates by default. To access a server with a self-signed certificate, you can instruct the tool to connect insecurely, or you can import the certificate into your client. Follow these steps to import the certificate into your client:

1.  Export the server certificate to a file:
    1.  On the computer that hosts the HCL UrbanCode Deploy server, open the server.xml file in a text editor. By default, this file is in the location server\_install/opt/tomcat/conf/server.xml. The default server installation directory is /opt/ucd/server on Linux™ and C:\\Program Files\\ucd\\server on Windows™.
    2.  In the server.xml file, find the following lines of code and note the values of the keystoreFile and keystorePass attributes:

        ```
        sslProtocol="TLS"
        keystoreFile="conf/tomcat.keystore"
        keystorePass="changeit" />
        ```

    3.  In a command-line window, run the following command:

        ```
        keytool -v -list -keystore keyStoreFileName
        ```

        The keytool application is included in the Java™ developer kit and is not part of HCL UrbanCode Deploy. Use the name of the keystoreFile attribute from the server.xml file for `keyStoreFileName`. When the command prompts you for a password, specify the value of the keystorePass attribute. The default value is `changeit`.

    4.  From the result of the command, find the alias of the server. For example, the result of the command might look like the following code:

        ```
        Keystore type: JKS
        Keystore provider: SUN
        
        Your keystore contains 1 entry
        
        Alias name: server
        Creation date: Mar 19, 2014
        Entry type: PrivateKeyEntry
        ```

        In this code, the alias is `server`.

    5.  Run the following command to export the certificate to a file and specify the password again:

        ```
        keytool -exportcert 
          -alias serverAlias 
          -keystore keyStoreFileName 
          -storetype jks 
          -file server.cert
        ```

        Use the alias of the server for `serverAlias`.

2.  Copy the server.cert file to the client computer.
3.  Import the server.cert file into the keystore of the client computer:
    1.  In a command-line window on the client computer, run the following command and specify the password for the keystore on the client. The default is `changeit`.

        ```
        jreLocation\jre\bin\keytool.exe -importcert 
          -alias serverAlias
          -file tomcat.cert 
          -storetype jks 
          -keystore jreLocation\jre\lib\security\cacerts
        ```

        Use the location of the JRE or JDK for `jreLocation.`


Now, some tools that use this JRE or JDK accept the server certificate. Other tools, such as `curl`, might still not accept the server certificate because it is unsigned. To resolve this problem, set up a signed certificate for the server.

**Parent topic:** [REST API reference](../../com.udeploy.reference.doc/topics/rest_api_ref_overview.md)

