# Customizing and verifying the TSO-ISPF client gateway

HCL® UrbanCode™ Deploy uses the IBM® z/OS® Time Sharing Option-Interactive System Productivity Facility \(TSO-ISPF\) gateway when it imports and deploys component versions.

You must install several PTF Services for the ISPF gateway to function correctly with the z/OS deployment tools. See the following technical support document for more information about: [http://www.ibm.com/support/docview.wss?uid=swg27042018](http://www.ibm.com/support/docview.wss?uid=swg27042018).

If you plan to run multiple deployments concurrently, install the following ISPF Client Gateway APAR corrections:

-   UA77460 - z/OS 1.13
-   UA77461 - z/OS 2.1

After you install the z/OS agent, customize and verify the TSO-ISPF client gateway by completing these steps:

1.   If the TSO-ISPF client gateway is not installed in the default location, customize the configuration by completing one of these steps: 
    -   If the TSO-ISPF client gateway is not installed in the default location, the path to the ISPF gateway executable file must be included in the PATH environment variable in OMVS. The default location of the TSO-ISPF client gateway is /usr/lpp/ispf/bin.
    -   If the ISP lib file is not installed in the default high-level qualifier \(ISP\), the ISPF.conf file must be updated with the correct high-level qualifier. The ISPF.conf file that HCL UrbanCode Deploy uses is in the agent install dir/conf/toolkit directory

2.   Test the TSO-ISPF client gateway: open the agent install dir/bin directory, and run this command: 

    ```
    startispf.sh time
    ```

    If the installation succeeded, the result of the TSO TIME command is displayed.

3.   Customize the ISPF.conf file to run your own programs or Restructured Extended Executor \(REXX\). If you plan to run programs or REXX executable files during a deployment by calling a TSO-ISPF command, add the program or REXX executable libraries to the concatenations in the ISPF.conf file. The ISPF.conf file that HCL UrbanCode Deploy uses in the agent install dir/conf/toolkit directory. In the ISPF.conf file, make load-module data sets available in the ISPLLIB concatenation, and make executable files available in the SYSPROC or SYSEXEC concatenations. For example, the following ISPF.conf file concatenations load modules for programs and REXX executable files. These modules are loaded: MYPROJ.MYCLIST, MYPROJ.MYREXX, and MYPROJ.LOAD.

    sysproc=ISP.SISPCLIB,hlq.SUCDEXEC,MYPROJ.MYCLIST  
     sysexec=ISP.SISPEXEC,MYPROJ.MYREXX  
     ispmlib=ISP.SISPMENU,hlq.SBUZMENU  
     isptlib=ISP.SISPTENU  
     ispplib=ISP.SISPPENU  
     ispslib=ISP.SISPSLIB  
     ispllib=ISP.SISPLOAD,MYPROJ.LOAD


**Parent topic:** [Installing the z/OS agent](../../com.udeploy.install.doc/topics/zos_installing_ov.md)

