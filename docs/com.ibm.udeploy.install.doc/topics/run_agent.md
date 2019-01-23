# Starting agents

To start an agent, run the shell script or batch file.

Make sure that the server is running. Also, if the agent runs through an agent relay, make sure that the relay is started.

1.  Go to the agent\_installation\\bin directory. 
2.  Run the appropriate script: 
    -   On Windows™, run this command:

        ```
        agent.cmd start
        ```

    -   On Linux™ or UNIX™, run this command:

        ```
        ./agent start
        ```

    -   On z/OS®, to run the agent as a started task, customize the sample `hlq.SBUZSAMP(BUZAGNT)` started task member, and then copy the task member to the `SYS1.PROCLIB` library. Provide the installation directory of the agent. The default installation directory of the agent is /opt/ucd/agent/bin. The following lines show sample code:

        ```
        //* 
        //* JES JOB MONITOR 
        //*
        //BUZAGNT  PROC AGENT='/opt/ucd/agent/bin'
        //*
        //BUZAGNT  EXEC PGM=BPXBATCH,REGION=0M,TIME=NOLIMIT,
        //            PARM='PGM &AGENT./agent run'
        //STDOUT   DD SYSOUT=*
        //STDERR   DD SYSOUT=*
        //*
        //        PEND
        //*
        ```

    -   On IBM® i, you must start the agent through the IBM Portable Application Solutions Environment for i \(PASE for i\) shell.
3.  After the agent starts, go to the HCL® UrbanCode™ Deploy web application, and under Resources, open the Agents page. 
4.   Associate the agent user ID to the started task by setting up the STARTED class profile. To set up the STARTED class, enter these commands: 

When the installation is complete, the agent is listed with a status of `Online`.

**Parent topic:** [Starting HCL UrbanCode Deploy](../../com.ibm.udeploy.install.doc/topics/runProduct.md)

