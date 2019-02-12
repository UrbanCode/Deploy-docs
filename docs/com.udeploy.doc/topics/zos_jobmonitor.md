# Job Monitor customization

The Job Monitor binary is installed with the IBM® z/OS® deployment tools in the hlq.SBUZAUTH data set. You need the assistance of a security administrator and a TCP/IP administrator to complete this customization task.

1.   Create a JCL file in a partitioned data set and base the file on the sample in the high\_level\_qualifier.SBUZSAMP\(BUZRJCL\) file. 
2.   Use the buztool createzosversion command to create the component version. 

    |Parameter|Required|Description|
    |---------|--------|-----------|
    |-c|true|The name of the component in HCL® UrbanCode™ Deploy. The component name can contain only letters, numbers, and spaces.|
    |-v|false|The name of the version to create. If a version is not specified, a version name is generated from the current time stamp. The version name can contain only letters, numbers, and spaces. **Note:** The version name must not end in a space.

|
    |-s|true|The location of the ship list file.|
    |-verb|false|To display a trace log, set this parameter to true.|

    For example, the following command creates a new version in the CICSModules component:

    ```
    buztool "createzosversion" "-c" "CICSModules" "-v" "fixbug100" "-s" "/u/ucduser/build/shiplist.xml"
    ```

    As shown, you must enclose all arguments in double quotation marks.

3.   Modify the sample file to reflect your system configuration. 
4.   Submit the JCL. 

The content that the ship list file specifies is available in a component in HCL UrbanCode Deploy.

**Parent topic:** [Installing the z/OS agent](../../com.udeploy.install.doc/topics/zos_installing_ov.md)

