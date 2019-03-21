# Creating z/OS component versions from z/OS UNIX System Services

To create IBM® z/OS® component versions from z/OS UNIX™ System Services, submit the buztool.sh command from a z/OS UNIX shell.

1.  Open a z/OS UNIX shell.
2.  Use the buztool.sh createzosversion command to create the component version.

    |Parameter|Required|Description|
    |---------|--------|-----------|
    |-c|true|The name of the component in HCL® UrbanCode™ Deploy. The component name can contain only letters, numbers, and spaces.|
    |-v|false|The name of the version to create. If a version is not specified, a version name is generated from the current time stamp. The version name can contain only letters, numbers, and spaces.|
    |-s|true|The location of the ship list file.|
    |-verb|false|To display a trace log, set this parameter to true|
    |-o|false|Full path name of the file where the output of version creation is written.|
    |-t|false|The type of the version to create. Set to full to create a full version. Default is incremental.|
    |-to|false|Provides the UCD token used to authenticate the UCD server. This token can be created by UCD user who has access to create versions in the corresponding component. If the token is not provided, buztool takes the token from the <agent\_home\>/conf/installed.properties\> server.tokenvalue to authenticate.|

    For example, the following command creates a new version in the CICSModules component:

    ```
    buztool.sh createzosversion -c CICSModules -v fixbug100 -s /u/ucduser/build/shiplist.xml
    ```

    If an argument contains spaces, enclose the argument in double quotation marks, as shown in the following example:

    ```
    buztool.sh createzosversion -c "CICS Modules" -v "fixbug 100" -s /u/ucduser/build/shiplist.xml
    ```


The content that the ship list file specifies is available in a component in HCL UrbanCode Deploy.

**Parent topic:** [Creating z/OS component versions](../topics/zos_runtools.md)

