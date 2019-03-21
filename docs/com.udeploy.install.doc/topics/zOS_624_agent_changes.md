# IBM z/OS agent changes in version 6.2.4

HCL® UrbanCode™ Deploy Version 6.2.4 includes several changes to make installing and using the z/OS® agent easier.

-   ****z/OS® deployment tools are packaged and installed with the agent****

    IBM® z/OS® deployment tools are a set of programs in both the UNIX™ file system and MVS™ data sets. The tools are used to import artifacts to z/OS® component versions and to deploy these versions. In version 6.2.3 and earlier, z/OS® deployment tools must be downloaded and installed in addition to the agent installation. In version 6.2.4, the z/OS® deployment tools are packaged with the z/OS® agent. The agent installer is updated to install both the agent and the z/OS® deployment tools in one process.

    The number of steps to install the product have been reduced if you install it interactively in the command-line interface. If you install the product in silent mode, review the new example.agent.install.properties file, and make sure you have the z/OS® deployment tools properties in this file too.

-   **Properties are consolidated into the installed.properties file**

    In versions 6.2.3 and earlier, a profile data set is used to store properties such as the high-level qualifier \(HLQ\) of the product, the CodeStation selection, and the security token. In version 6.2.4 and later, these properties are consolidated into the installed.properties file, which is located in the agent install dir/conf/agent. The upgrade installer automatically migrates the properties to the new location.

    The token that is stored in the installed.properties file is encrypted after its first use.

-   **Directories for repositories, deployments, and logs**

    In version 6.2.4, the installer does not request the repository directory location, deployment directory, or ISPF log directory. The following default values are used:

    -   agent install dir/var/repository
    -   agent install dir/var/deploy
    -   agent install dir/var/log/ispf
    If you must use different directories, you can use symbolic links to link to the target directories. The upgrade installer automatically creates the symbolic links if the previous installation uses different directories.

-   **A new test script to verify version imports**

    A new test-create-version.sh script is provided to test the version import after agent installation. When the version import succeeds, the script creates two versions of the component that is called MYCOMP by using sample ship lists. To use the test script, you have to create a z/OS® type component called MYCOMP.

    The test script is located in agent install dir/bin/test-create-version.sh.

    The ship lists are located in agent install dir/zossamples folder.

-   **A new required BUZTOOL parameter to use when you are running the tool in JCL**

    To run BUZTOOL in JCL to import versions, a new parameter -agent must be provided with the value of the agent installation directory. See following for example:

    `//SYSTSIN DD *  
     ISPSTART CMD(BUZTOOL "createzosversion" -  
           "-c" "ComponentName" -  
           "-s" "ShipListPathname" -  
          **"-agent" "/opt/ibm-ucd/agent"**)  
     /*`

-   **The z/OS® File Source Config plug-in is installed by default**

    The z/OS® File Source Config plug-in automates uploading data sets, UNIX™ files, and generic artifacts from a z/OS® system into a component version. It provides a Web UI to run the z/OS® deployment tools commands. To import a version by using the z/OS® File Source Config plug-in, configure your component to use the Source Config plug-in, and then click the **Import New Versions** push button in the versions view to start a new import.


**Parent topic:** [Upgrading IBM z/OS agents](../../com.udeploy.install.doc/topics/upgrade_zOS_agents.md)

