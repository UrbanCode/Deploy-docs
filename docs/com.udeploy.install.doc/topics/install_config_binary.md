# Installing the binary and config files to different directories

By default, the agent installer installs the binary and config files into the same directory. You can customize the installation so that these files are installed into different directories. Also, multiple agent configurations can share the same copy of binary files which makes security control and product upgrading easier.

## Installing agent binary files

Agent binary files are installed by running the agent-install.sh script with the **-binary** parameter. Note that all agent data sets are considered binary files. Depending on the installation method, agent data sets are either installed by the SMP/E process or by submitting the BUZEXPD job.

After the binary files are installed, they can be used by multiple agents. Typically, they are installed to a shared volume and made accessible by multiple systems in read-only mode.

## Installing agent config files

Agent config files are installed by running the agent-install.sh script with the **-config** parameter. The installation program prompts you to specify the directory of the agent binary before installation the process can start. You should specify a different directory for the agent config.

The HFS CodeStation and the deploy backup directories are also located in the agent config directory. The storage space calculation described in the [Choosing a CodeStation and planning storage](codestation_choose_plan.md) topic applies to the agent config directory.

## Upgrading agent

In the binary and config installation mode, only the agent binary needs to be upgraded. When needed the agent config is automatically upgraded, when you start the agent or run the buztool.sh script.

## Limitations

The following are limitations related to the binary and config installation mode.

-   Upgrading agents from the Web user interface is not supported for agents installed using the binary and config mode.
-   The binary and config installation mode can only be used when installing new agents.
-   Silent mode installation using install-agent-from-file.sh does not support binary and config mode.
-   Config files must be installed using the install-agent.sh script. It is not supported to copy files or data sets to other locations.

**Parent topic:** [Installing the z/OS agent](../../com.udeploy.install.doc/topics/zos_installing_ov.md)

**Parent topic:** [Installing the z/OS agent](../../com.udeploy.install.doc/topics/zos_installing_ov.md)

