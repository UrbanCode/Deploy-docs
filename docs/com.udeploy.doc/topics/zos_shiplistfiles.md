# Ship list files

The ship list file describes the files from the build to include in the new component version to deploy. Ship list files can also use generic artifacts to describe changes that are not physical files, such as configuration changes.

You must create a ship list file before you run the IBM® z/OS® deployment tools. Typically, you write a script that works with your build engine to create a ship list file from the build output. Ship list files are XML files that contain a list of file specifiers.

## Partitioned data sets

Partitioned data set \(PDS\) members are identified by the PDS container type and the PDSmember resource type. You can use an asterisk \(\*\) as a wildcard for the resource name, if you want all members in a partitioned data set to be included in a package.

For example, to package the BLZCPBTK member from the BLD.JCL PDS and all of the members in the BLD.LOAD1 PDS and the ORDRSET and RDBKC01 members from the BLD.LOAD2 PDS, the ship list file might contain the following lines:

```
<?xml version="1.0" encoding="CP037"?>
<manifest type="MANIFEST_SHIPLIST">
    <container name="BLD.JCL" type="PDS">
        <resource name="BLZCPBTK" type="PDSMember"/>
    </container>
    <container name="BLD.LOAD1" type="PDS">
        <resource name="*" type="PDSMember"/>
    </container>
    <container name="BLD.LOAD2" type="PDS">
        <resource name="ORDRSET" type="PDSMember"/>
        <resource name="RDBKC01" type="PDSMember"/>
    </container>
</manifest>
```

## Sequential data sets

Sequential data sets are identified by the sequential container type.

For example, to package the BLD.DATA1 sequential data set, the ship list file might contain the following lines:

```
<?xml version="1.0" encoding="CP037"?>
<manifest type="MANIFEST_SHIPLIST">
    <container name=" BLD.DATA1" type="sequential">
    </container>
</manifest>
```

## HFS files

Hierarchical file system \(HFS\) files used in z/OS UNIX are identified by the directory container type and the file resource type. Both container name and resource name support the Ant file include pattern. \(For more information about Ant, see [https://ant.apache.org/](https://ant.apache.org/).\) Each directory container must use the rootDir attribute to identify the root directory to resolve files from. Only files in that root directory are considered.

For example, to package \*.wsbind files and \*.wsdl files from the wsbind directory and the wsdl directory within the root directory /u/dave/cicsfiles, the ship list file might contain the following lines:

```
<?xml version="1.0" encoding="CP037"?>
<manifest type="MANIFEST_SHIPLIST">
    <container name="wsbind" rootDir="/u/dave/cicsfiles" type="directory">
        <resource name="*.wsbind" type="file"/>
    </container>
    <container name="wsdl" rootDir="/u/dave/cicsfiles" type="directory">
        <resource name="*.wsdl" type="file"/>
    </container>
</manifest>
```

To package everything from the root directory /u/dave/cicsfiles, the ship list file might contain the following lines:

```
<?xml version="1.0" encoding="CP037"?>
<manifest type="MANIFEST_SHIPLIST">
    <container name="." rootDir="/u/dave/cicsfiles" type="directory">
        <resource name="**/*" type="file"/>
    </container>	
 </manifest>
```

To deploy HFS files, use the same plug-in steps as you use to deploy data sets. HFS files and data sets can be put into the same version and deployed or rolled back together.

## Deployment types

You can set the deployType attribute on containers and resources. The deployType attribute is used to identify different types of artifacts so that they can be processed differently during a deployment. The following ship list file shows deployType attributes that are added to the previous PDS example:

```
<?xml version="1.0" encoding="CP037"?>
<manifest type="MANIFEST_SHIPLIST">
    <container name="BLD.JCL" type="PDS" deployType="JCL">
        <resource name="BLZCPBTK" type="PDSMember"/>
    </container>
    <container name="BLD.LOAD1" type="PDS" deployType="CICS LOAD">
        <resource name="*" type="PDSMember"/>
    </container>
    <container name="BLD.LOAD2" type="PDS">
        <resource name="ORDRSET" type="PDSMember" deployType="CICS LOAD"/>
        <resource name="RDBKC01" type="PDSMember" deployType="CICS LOAD"/>
    </container>
</manifest>
```

## Custom properties

You can add custom properties to containers and resources. The properties are displayed in the Version Artifacts view and can be used by plug-in steps. For example, properties can be used by the Generate Artifact Information step in the IBM z/OS Utility plug-in. The following ship list file shows an example of custom properties.

```
<?xml version="1.0" encoding="CP037"?>
<manifest type="MANIFEST_SHIPLIST">
    <container name="BLD.DBRM" type="PDS">
        <property name="COLLID" value="C001"/>
        <resource name="MOD01" type="PDSMember">
            <property name="devowner" value="Martin"/>
        </resource>
    </container>
</manifest>
```

You can add custom properties to the manifest element. When a property is the child of the manifest element, it is created as a component version property. If the value of the property is a URL, a link is added to the version.

To learn more about using custom properties, see "Using custom properties in deployments" in the [IBM z/OS Utility plug-in documentation](https://developer.ibm.com/urbancode/plugindoc/ibmucd/zos-utility-plug/).

## Deletions

You can mark PDS members, sequential data sets, or HFS files for deletion by specifying the containers inside a deleted element. Data sets or HFS files that are marked for deletion are deleted from the target environment when the deployment process runs. The deleted artifacts can be rolled back if the backup option is enabled in the deployment step. If you use the ship list file to delete data sets, you can roll back the deletions as needed.

For example, the following ship list deploys PGM1 and PGM2 and deletes PGM3 from the target environment:

```
<?xml version="1.0" encoding="CP037"?>
<manifest type="MANIFEST_SHIPLIST">
    <container name="BLD.LOAD1" type="PDS">
        <resource name="PGM1" type="PDSMember"/>
        <resource name="PGM2" type="PDSMember"/>
    </container>
<deleted>
    	<container name="BLD.LOAD1" type="PDS">
        	<resource name="PGM3" type="PDSMember"/>
	</container>
</deleted>
</manifest>
```

## Generic artifacts

Use generic artifacts to describe changes to deploy that are not physical files. For example, use generic artifacts to deploy system configuration changes or middleware configuration changes that are not associated with standard artifacts. Generic artifacts have the `GENERIC` container type.

For example, the following ship list describes two message queues to deploy to the target environment:

```
<?xml version="1.0" encoding="CP037"?>
<manifest type="MANIFEST_SHIPLIST">
<container name="QLOCAL" type="GENERIC" deployType="">
  <resource name="LCQ1">
    <property name="maxdepth" value="5000"/>
  </resource>
  <resource name="LCQ2">
    <property name="maxdepth" value="200000"/>
  </resource>
</container>
```

To deploy generic artifacts, use the Generate Artifact Information step from the z/OS Utility plug-in to generate commands for deploying the artifacts. Then, use an appropriate command step to run the commands. Steps that you can use to run commands include the Submit Job step, the Shell step, and the TSO/ISPF Command step. Other plug-ins can also use the output of the Generate Artifact Information step to deploy changes.

## Source information

You can add source information to PDS members and sequential data sets to build traceability from deployable artifacts to the source code version. The source information is displayed in appropriate views in the HCL® UrbanCode™ Deploy server.

In following example, the source information in the `<inputs>` and `<input>` elements indicate `BLD.LOAD(ORDRSET)` is compiled from two source code files, a main program ORDERSET and a copybook ORDRDATA. The version of the source code is identified by the version attribute.

```
<?xml version="1.0" encoding="CP037"?>
<manifest type="MANIFEST_SHIPLIST">
    <container name="BLD.LOAD" type="PDS">
        <resource name="ORDRSET" type="PDSMember">
<inputs url="">
<input name="ORDRSET" version="3" compileType="Main" url = ""/>
                <input name="ORDRDATA" version="1" compileType="Copybook" url = ""/>
             </inputs>
	</resource>
    </container>
</manifest>

```

**Note:** 

-   The ship list file must be encoded in CP037 format.
-   In deletions, wildcards must not be used for directory or file names.
-   If a data set member name contains invalid characters, the characters are replaced by % to match any characters. Valid data set member name characters are `0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ@#$`.

**Parent topic:** [Deploying components to the z/OS platform](../topics/deploying_zos.md)

