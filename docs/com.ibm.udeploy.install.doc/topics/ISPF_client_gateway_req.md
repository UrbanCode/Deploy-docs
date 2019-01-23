# ISPF client gateway requirements

HCL® UrbanCode™ Deploy uses the z/OS® Time Sharing Option-Interactive System Productivity Facility \(TSO-ISPF\) gateway when it imports and deploys component versions.

You must install several PTF Services for the ISPF gateway to function correctly with the z/OS deployment tools. See the following technical support document for more information about: [http://www.ibm.com/support/docview.wss?uid=swg27042018](http://www.ibm.com/support/docview.wss?uid=swg27042018).

If you plan to run multiple deployments concurrently, install the following ISPF Client Gateway APAR corrections:

-   UA77460 - z/OS 1.13
-   UA77461 - z/OS 2.1

After you install the z/OS agent, customize and verify TSO/ISPF client gateway by completing these steps:

1.  Customize the configuration if the TSO/ISPF client gateway is not installed in the default location.
    1.  If the TSO/ISPF client gateway is not installed to the default location, the directory to the ISPF gateway executable file must be included in the PATH environment variable in OMVS. The default location of the TSO/ISPF client gateway is the /usr/lpp/ispf/bin directory.
    2.  If the ISP library is not installed in the default high-level qualifier \(ISP\), the ISPF.conf file must be updated with the correct high-level qualifier. The ISPF.conf file that HCL UrbanCode Deploy uses is in the agent install dir/conf/toolkit directory.
2.  To test the TSO/ISPF client gateway, go the agent install dir/bin directory, and run this command:

    ```
    startispf.sh time
    ```

    If the command succeeds, the result of the TSO TIME command is displayed.

3.  Customize the ISPF.conf file to run your own programs or REXX.

    If you plan to run programs or REXX executable files during a deployment by calling a TSO/ISPF command, add the program or REXX executable libraries to the concatenations in the ISPF.conf file. In the ISPF.conf file, make load-module data sets available in the ISPLLIB concatenation, and make executable files available in the SYSPROC or SYSEXEC concatenations. For example, the following ISPF.conf file concatenations load modules for programs and REXX executable files. The modules that are loaded are MYPROJ.MYCLIST, MYPROJ.MYREXX, and MYPROJ.LOAD

    -   sysproc=ISP.SISPCLIB,hlq.SUCDEXEC,MYPROJ.MYCLIST

    -   sysexec=ISP.SISPEXEC,MYPROJ.MYREXX

    -   ispmlib=ISP.SISPMENU,hlq.SBUZMENU

    -   isptlib=ISP.SISPTENU

    -   ispplib=ISP.SISPPENU

    -   ispslib=ISP.SISPSLIB

    -   ispllib=ISP.SISPLOAD,MYPROJ.LOAD
    The ISPF.conf file that HCL UrbanCode Deploy uses is in the agent install dir/conf/toolkit directory.


**Parent topic:** [Installing the z/OS agent](../../com.ibm.udeploy.install.doc/topics/zos_installing_ov.md)

