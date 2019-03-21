# Starting z/OS agents from the z/OS UNIX command line

The UCD z/OS agent can be started from ISPF as a started task or from the z/OS UNIX command line. To start an agent from ISPF as a started task refer to [Starting agents](run_agent.md). To start the z/OS agent from the z/OS UNIX command line, follow this procedure.

Make sure that the server is running. Also, if the agent runs through an agent relay, make sure that the relay is started.

1.   Login to the z/OS UNIX shell using the TSO OMVS command or by using a TELNET client. 
2.   Go to the agent\_install\_dir/bin directory. 
3.   Run the following script: 

    ```
    ./agent start
    ```

    To stop the agent, run the following script from the same directory:

    ```
    ./agent.stop
    ```


When the agent is started from the command line, the current login user ID is used as the agent user ID.

**Parent topic:** [Starting HCL UrbanCode Deploy](../../com.udeploy.install.doc/topics/runProduct.md)

**Parent topic:** [z/OS considerations for UrbanCode Deploy](../../com.udeploy.doc/topics/zos_ch.md)

