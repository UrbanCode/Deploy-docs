# Deploying to the z/OS platform

Use the toolkit to deploy to the IBM® z/OS® platform.

Deploying to the IBM z/OS platform is similar to deploying to other platforms. Create an application, components, environments, and resources. Import versions of artifacts to the components, and then create an application process that deploys the components to a target environment. When you create a component for z/OS artifacts, select **z/OS** as the component type.

Versions can be imported to a z/OS component by using the zOS File source configuration plug-in or by using the buztool command line from an z/OS agent.

1.   Install the z/OS agent. 
2.  Create a ship list file.See [Ship list files](zos_shiplistfiles.md).
3.  Create a deployable component version.See [Creating z/OS component versions](zos_runtools.md).
4.   Create component processes and application processes as you would for any other deployment, by using the z/OS Utility plug-in for process steps that retrieve and deploy z/OS artifacts. For example, use Download Artifacts for z/OS process steps to retrieve z/OS artifacts. Use the Deploy Data Set process step to deploy z/OS data sets and HFS files. The z/OS Utility plug-in also includes process steps for rolling back data sets, for running commands from the time sharing option \(TSO\) command line, and for running ISPF commands. To learn more about the z/OS Utility plug-in, see the HCL® UrbanCode™ Deploy [plug-in site](http://developer.ibm.com/urbancode/plugins/ibm-urbancode-deploy/). It is also recommended to create component using the MVSCOMPONENT template which has built-in deploy processes.

-   **[Ship list files](../topics/zos_shiplistfiles.md)**  
The ship list file describes the files from the build to include in the new component version to deploy. Ship list files can also use generic artifacts to describe changes that are not physical files, such as configuration changes.
-   **[Searching the z/OS environment inventory](../topics/zos_search_inventory.md)**  
The z/OS search feature is available for any application that contains a z/OS type component. Search is performed for a specific file in the artifacts belonging to the z/OS components deployed to that environment.
-   **[Creating z/OS component versions](../topics/zos_runtools.md)**  
You can create z/OS component version by running the buztool.sh command from job control language \(JCL\) or from the z/OS UNIX System Services command line. You can also create z/OS component version by using the z/OS File Source Config plug-in.

**Parent topic:** [Installing the z/OS agent](../../com.udeploy.install.doc/topics/zos_installing_ov.md)

**Parent topic:** [z/OS considerations for UrbanCode Deploy](../topics/zos_ch.md)

**Parent topic:** [Deploying](../topics/deployment_ov.md)

