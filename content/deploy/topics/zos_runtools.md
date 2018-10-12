# Creating z/OS component versions {#zos_runtools .task}

You can create z/OS component version by running the buztool.sh command from job control language \(JCL\) or from the z/OS® UNIX™ System Services command line. You can also create z/OS component version by using the z/OS File Source Config plug-in.

In an automated system, typically, you write a script that runs the buztool.sh command after a build is created by your build system. The buztool.sh command then creates a component version which can be deployed using a deploy process.

You can work with the component that contains z/OS files as you would work with any other component in IBM® UrbanCode® Deploy. Use the z/OS Utility plug-in to create processes that deploy components that contain z/OS files. See the IBM UrbanCode Deploy website for information about the z/OS Utility plug-in: [IBM UrbanCode Deploy](https://developer.ibm.com/urbancode/plugins/ibm-urbancode-deploy/).

-   **[Creating z/OS component versions from JCL](../topics/zos_runtools_jcl.md)**  
To create IBM z/OS component versions from job control language \(JCL\), create and submit JCL to run the buztool.sh command.
-   **[Creating z/OS component versions from z/OS UNIX System Services](../topics/zos_runtools_uss.md)**  
To create IBM z/OS component versions from z/OS UNIX System Services, submit the buztool.sh command from a z/OS UNIX shell.

**Parent topic:** [Deploying to the z/OS platform](../topics/deploying_zos.md)

