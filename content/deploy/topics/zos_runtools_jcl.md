# Creating z/OS component versions from JCL {#zos_runtools_jcl .task}

To create IBM® z/OS® component versions from job control language \(JCL\), create and submit JCL to run the buztool.sh command.

**Note:** The JCL to run buztool.sh is changed in IBM UrbanCode® Deploy 6.2.5 to use the BPXBATCH utility. The JCL created before version 6.2.5 needs to be updated to follow the format in the new example.

1.  Create a JCL file in a partitioned data set and base the file on the sample in the high\_level\_qualifier.SBUZSAMP\(BUZRJCL\) file. 
2.   Use the buztool.sh createzosversion command to create the component version. 

    |Parameter|Required|Description|
    |---------|--------|-----------|
    |-c|true|The name of the component in IBM UrbanCode Deploy. The component name can contain only letters, numbers, and spaces.|
    |-v|false|The name of the version to create. If a version is not specified, a version name is generated from the current time stamp. The version name can contain only letters, numbers, and spaces.|
    |-s|true|The location of the ship list file.|
    |-verb|false|To display a trace log, set this parameter to true.|
    |-o|false|Full path name of the file where the output of version creation is written.|
    |-t|false|The type of the version to create. Set to full to create a full version. Default is incremental.|

    For example, the following command creates a new version in the CICSModules component:

    ```
    /opt/ibm-ucd/agent/bin/buztool.sh "createzosversion" "-c" "CICSModules" "-v"
            "fixbug100" "-s" "/u/ucduser/build/shiplist.xml"
    ```

    As shown, you must enclose all arguments in double quotation marks.

3.  Modify the sample file to reflect your system configuration. 
4.  Submit the JCL.

The content that the ship list file specifies is available in a component in IBM UrbanCode Deploy.

**Parent topic:** [Creating z/OS component versions](../topics/zos_runtools.md)

