# Installing the z/OS agent

Before you deploy to the IBM® z/OS® platform, you must install the z/OS agent and configure the z/OS server for communication with HCL® UrbanCode™ Deploy. If the build process runs on a different logical partition \(LPAR\), then you must additionally install the agent on the build LPAR. You can install the z/OS agent and deployment tools by using the IBM System Modification Program Extended \(SMP/E\) or by extracting archive files to the z/OS UNIX™ file system.

**Note:** Beginning with version 6.2.4. the z/OS deployment tools have become part of the z/OS agent. The deployment tools no longer require a separate installation. If you are upgrading from a version earlier than 6.2.4, see [Upgrading IBM z/OS agents](upgrade_zOS_agents.md#) for details about the changes.

Review the system requirements, and then plan the installation:

-   Review [Choosing a CodeStation and planning storage](codestation_choose_plan.md#).
-   Review [Security requirements on IBM z/OS computers](../../com.udeploy.admin.doc/topics/security_zos.md#).
-   Review [ISPF client gateway requirements](ISPF_client_gateway_req.md#).
-   Review [Installing the binary and config files to different directories](install_config_binary.md).

1.   To install the agent by using SMP/E, complete these steps: 
    1.   Install the z/OS agent by using SMP/E. See [Installing the z/OS agent and deployment tools by using SMP/E](../../com.udeploy.doc/topics/zos_installing_smpe.md). 
    2.   Install agents from the command line. See [Installing agents from the command line](agentInstall.md), and start with step 3. 
2.   To install by extracting files to the z/OS UNIX file system, see [Installing agents from the command line](agentInstall.md). 

-   **[Installing the z/OS agent and deployment tools by using SMP/E](../../com.udeploy.doc/topics/zos_installing_smpe.md)**  
IBM System Modification Program/Extended \(SMP/E\) is a tool for installing and maintaining software on z/OS systems. SMP/E controls software changes at the element level. Job Control Language \(JCL\) is submitted by using 3270 emulation.
-   **[Deploying by using the Job Monitor](../../com.udeploy.install.doc/topics/zos_using_job_monitor.md)**  
You use the Job Monitor to submit jobs and to monitor the job status in your deployment. You must ensure that you have a Job Monitor task running and that you run the Urban Code Deploy process to submit or to monitor the job. Then, you must set up Job Monitor connection properties in your HCL UrbanCode Deploy environment.
-   **[Job Monitor customization](../../com.udeploy.doc/topics/zos_jobmonitor.md)**  
The Job Monitor binary is installed with the IBM z/OS deployment tools in the hlq.SBUZAUTH data set. You need the assistance of a security administrator and a TCP/IP administrator to complete this customization task.
-   **[Choosing a CodeStation and planning storage](../../com.udeploy.doc/topics/codestation_choose_plan.md)**  
After installation, you can change the CodeStation where version artifacts are stored. The IBM z/OS agent that is used to import version stores artifact versions when the choice of CodeStation is HFS. Every z/OS agent that is used to deploy projects stores backups of old artifacts so that a rollback can be done when required. Plan the agent directory to ensure there is sufficient space for CodeStation and backup.
-   **[Customizing and verifying the TSO-ISPF client gateway](../../com.udeploy.doc/topics/ISPF_client_gateway_req.md)**  
HCL UrbanCode Deploy uses the IBM z/OS Time Sharing Option-Interactive System Productivity Facility \(TSO-ISPF\) gateway when it imports and deploys component versions.
-   **[Installing the binary and config files to different directories](../../com.udeploy.install.doc/topics/install_config_binary.md)**  
By default, the agent installer installs the binary and config files into the same directory. You can customize the installation so that these files are installed into different directories. Also, multiple agent configurations can share the same copy of binary files which makes security control and product upgrading easier.

**Parent topic:** [z/OS considerations for UrbanCode Deploy](../../com.udeploy.doc/topics/zos_ch.md)

