# Upgrading IBM z/OS agents

You can upgrade IBM® z/OS® agents. However, you must upgrade the server before you upgrade the agents.

Depending on how the z/OS agents are installed, you have several options for upgrading the agents.

If you are upgrading to version 6.2.4 from a previous version, review [IBM z/OS agent changes in version 6.2.4](zOS_624_agent_changes.md#).

If you are upgrading to version 6.2.4 from a version earlier than 6.1.1, see [Migrating data from versions before 6.1.1](migrate_b4_611.md#).

1.   To upgrade from SMP/E installation, complete these steps: 

    1.   If a different high-level qualifier than that for the previous installation is used, edit each agent's installed.properties file, specifying the new high-level qualifier. 
    2.   Follow the instructions in the Program Directory for HCL® UrbanCode™ Deploy for z/OS. 
    3.   Upgrade each agent by using one of the options in [Upgrading agents](upgradeAgents.md#) 
    **Note:** 

    After the SMP/E installation, the UNIX installer is already on your file system so you can skip the first few steps in the typical command-line install or upgrade guide and start from running the shell commands. If you are following the instructions in [Upgrading agents from the command line](upgrade_agent_cli.md#) or [Upgrading agents in silent mode](upgrade_agent_silent.md#) topics, you can skip the steps that download and extract the installer. Start with running the install-agent.sh or install-agent-from-file.sh script from your SMP/E installation directory.

2.   To upgrade from a non-SMP/E installation, complete these steps: 
    1.   Upgrade by using one of the options in [Upgrading agents](upgradeAgents.md#). 
    2.   Submit a job to load the agent data sets. Locate the job JCL at agent install dir/mvs/BUZEXPD. The JCL, except the job parameter, is already customized, based on the agent configuration. Edit and submit the job to load the agent data sets. For example, use the following commands in OMVS to edit or submit the JCL: 

        ```
        oedit agent install dir/mvs/BUZEXPD
        submit agent install dir/mvs/BUZEXPD
        ```


-   **[IBM z/OS agent changes in version 6.2.4](../../com.udeploy.install.doc/topics/zOS_624_agent_changes.md)**  

-   **[Migrating data from versions before 6.1.1](../../com.udeploy.install.doc/topics/migrate_b4_611.md)**  
Upgrade the server, agents, and agent relays before upgrading the IBM z/OS deployment tools.
-   **[IBM z/OS agent changes in version 6.2.4](../../com.udeploy.install.doc/topics/zOS_624_agent_changes.md)**  

-   **[Migrating data from versions before 6.1.1](../../com.udeploy.install.doc/topics/migrate_b4_611.md)**  
Upgrade the server, agents, and agent relays before upgrading the IBM z/OS deployment tools.

**Parent topic:** [Upgrading agents](../../com.udeploy.install.doc/topics/upgradeAgents.md)

**Parent topic:** [Installing the z/OS agent](../../com.udeploy.install.doc/topics/zos_installing_ov.md)

**Parent topic:** [z/OS considerations for UrbanCode Deploy](../../com.udeploy.doc/topics/zos_ch.md)

