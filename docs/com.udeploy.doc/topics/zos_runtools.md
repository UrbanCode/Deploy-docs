# Creating z/OS component versions

You can create z/OS component version by running the buztool.sh command from job control language \(JCL\) or from the z/OS® UNIX™ System Services command line. You can also create z/OS component version by using the z/OS File Source Config plug-in.

In an automated system, typically, you write a script that runs the buztool.sh command after a build is created by your build system. The buztool.sh command then creates a component version which can be deployed using a deploy process.

You can work with the component that contains z/OS files as you would work with any other component in HCL® UrbanCode™ Deploy. Use the z/OS Utility plug-in to create processes that deploy components that contain z/OS files. See the HCL UrbanCode Deploy website for information about the z/OS Utility plug-in: [HCL UrbanCode Deploy](https://developer.ibm.com/urbancode/plugins/ibm-urbancode-deploy/).

-   **[Creating z/OS component versions from JCL](../topics/zos_runtools_jcl.md)**  
To create IBM® z/OS component versions from job control language \(JCL\), create and submit JCL to run the buztool.sh command.
-   **[Creating z/OS component versions from z/OS UNIX System Services](../topics/zos_runtools_uss.md)**  
To create IBM® z/OS component versions from z/OS UNIX System Services, submit the buztool.sh command from a z/OS UNIX shell.
-   **[Merging z/OS component versions](../topics/zos_merge_comp.md)**  
Two or more z/OS component versions can be merged from a snapshot into one component version to simplify the deployment to the next environment. Merging component versions in this way avoids deploying intermediate programs into production.

**Parent topic:** [Deploying components to the z/OS platform](../topics/deploying_zos.md)

**Related information**  


[https://developer.ibm.com/urbancode/docs/property-overview-ibm-urbancode-deploy-zos/](https://developer.ibm.com/urbancode/docs/property-overview-ibm-urbancode-deploy-zos/)

[https://developer.ibm.com/urbancode/2017/01/09/managing-properties-using-ucd-build-mainframe-applications/](https://developer.ibm.com/urbancode/2017/01/09/managing-properties-using-ucd-build-mainframe-applications/)

