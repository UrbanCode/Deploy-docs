# Installing the command-line client

The command-line client is available in an archive file that you can download from the server.

Make sure that the JAVA\_HOME system variable is set to the location of a JRE or JVM.

Beginning with HCL® UrbanCode™ Deploy version 6.1, the command-line client is installed on agents automatically. The client is in the folder agent\_install/opt/udclient.

1.  To install the tool, download the udclient.zip file to the system on which you want to use the tool. You can download the file from the HCL UrbanCode Deploy server by clicking **Help** \> **Tools** and then clicking **HCL UrbanCode Deploy Client**. You can also find the file in the folder server\_install/opt/tomcat/webapps/ROOT/tools/, where server\_install is the installation folder for the server.
2.  Extract the file.
3.  Set system variables such as DS\_WEB\_URL so you do not have to specify credentials each time you run a command. See [Command format](cli_command_format.md).

For information about specific commands, see [CLI Commands](cli_commands.md).

**Parent topic:** [Command-line client \(CLI\) reference](../../com.ibm.udeploy.reference.doc/topics/cli_ch.md)

