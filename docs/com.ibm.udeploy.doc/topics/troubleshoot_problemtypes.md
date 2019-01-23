---
keyword: [troubleshoot, problem types]
---

# Types of problems and checks to perform

Before you contact IBM Software Support, gather background information and perform tasks that will assist in solving the problem. It helps to be as specific as possible and include all relevant information.

[Table 1](#problem_types) lists several problem categories. The information in the table guides you on checks to perform and data to gather.

|Problem Type|Descriptions|What to do|
|------------|------------|----------|
|Database|Database errors tend to show up on the server. Look for server errors which appear to be specific to databases, for example: ORA0001 Constraint Violation.|[Troubleshooting database problems](#database_problems)|
|Integration with other products HCL® UrbanCode™ Deploy|Attempts to connect to IBM® Cloud Orchestrator, IBM PureApplication® System, or IBM Workload Deployer to provision an image results in one of the following: -   Errors
-   No image is created
-   Agent cannot be contacted

 |[UrbanCode Deploy integration with Cloud providers \(classic\)](http://www-01.ibm.com/support/docview.wss?uid=swg21661921)|
|Attempts to integrate with LDAP for user authentication and authorization produce unexpected results.|[Integation with LDAP](http://www-01.ibm.com/support/docview.wss?uid=swg21680342)|
|Performance|Excessive page load times, processes taking longer than normal, and other time related problems.|[Troubleshooting performance problems](#performance_problems)|
|Plug-ins|Plug-in steps are not functioning as expected.|[Troubleshooting plug-in problems](#plugin_problems)|
|Server|Errors specific to the server. Errors in the deployserver.out file. Or, HTTP requests which return with the response code 500 Internal Server Error.|[Troubleshooting server problems](#server_problems)|
|User Interfaces|Pages are not rendering completely.|[Troubleshooting user interface problems](#interface_problems)|

## Troubleshooting agent problems

For issues that appear to be specific to an agent, collect the following:

-   <agent\>/conf/agent/installed.properties 
-   <agent\>/conf/installed.version 
-   <agent\>/conf/plugin-javaopts.conf 
-   <agent\>/var/log/agent.out

For problems were the agent is not able to show **Online**, when viewing the status in the server user interface.

1.  Add the following trace string to the agent <agent\>/conf/agent/ log4j.propertiesfile:

    ```
    log4j.logger.com.urbancode.air.agent=DEBUG log4j.logger.com.urbancode.air.devilfish=DEBUG 
    ```

2.  Add the following trace string to the server in the product user interface. Click **System Settings****Logging** and add the following:

    ```
    log4j.logger.com.urbancode.ds.subsys.deploy.agent=DEBUG log4j.logger.com.urbancode.air.devilfish=DEBUG
    ```

3.  Stop the agent and then start the agent.
4.  Send all the logs from <agent\>\\var\\logs to support.
5.  Send the <server\>\\var\\log\\deployserver.out from the server or servers if running a high availability configuration to support.

## Troubleshooting database problems

For issues that appear to be specific to the database include the database type and version. Additionally, ensure that your database administrator is available to perform diagnostic on the database server, as requested by IBM Support.

If the issue is related to a user application process or component process capturing screen shots of the process and the step properties of steps that are failing are useful.

## Remote Agent Upgrade Issues

For problems when upgrading an agent remotely from the server fails and leaves the agent offline, if possible produce the problem again and collect trace data.

1.  Add the following trace string to the agent log4j.properties file:

    ```
    log4j.logger.com.urbancode.air.mw = DEBUG 
    ```

2.  Perform the upgrade again. Hopefully, the problem occurs to collect trace data.

If the issue has already occurred, collect the following information:

1.  Check the agent bin directory for the upgrade.out file. If the file exists, send the file to support.
2.  Check if there is a directory in the bin directory called agent-upgrade and if there are any files inside it . Send a directory listing to support.
3.  Check if there is a file called upgrade.jarinside the agent's bin folder. Provide the size of that file to support.
4.  Send all the logs from <agent\>\\var\\logsto support.
5.  Send all the files from <agent\>\\conf\\agent to support.
6.  Check if there are any java processes running:
    -   For Linux issue the following command: ps -ef |grep java
    -   For Windows use the Task Manager

Verify the complete command line commands of those processes to make sure that they belong to the agent. The agent normally has two running processes; the monitor and the worker.

## Troubleshooting performance problems

Symptoms indicating a performance problem includes: excessive page load times, processes taking longer than normal, and other time-related problems.

If user interface pages are loading slowly, do the following:

-   Use the browser console or tools such as the Google Chrome Developer Console to load the page and check the response times for the HTTP requests and responses. For HCL UrbanCode Deploy version 6.1.0.2 or higher, this information can be viewed from the user interface.
    1.  Log into the HCL UrbanCode Deploy server.
    2.  Click **Settings** \> **System** \> **Diagnostics**. The Diagnostics page logs the amount of time HTTP requests take.

If the server is operating slowly, gather a set of thread dumps from the server. Ensure there is some time distance between them ranging from a few seconds to a minute.

**Note:** An IBM Support representative might request that you collect heap dumps. Do not perform this action if not requested because heap dumps can cause a large JVM pause.

## Troubleshooting plug-in problems

The primary symptoms of plug-in related problems is that the plug-in is not functioning as expected. There can also be issues with connections to other servers that the plug-in uses.

Before contacting IBM Software Support verify that the plug-in steps are being used correctly and the required properties are specified.

If you are experiencing problems installing the plug-in, you will need information about the server. For other problems, collect the following information:

-   Description of how the plug-in is integrated. Is it a built-in or added plug-in.
-   The full plug-in version including build number. This information is located in the info.xml file.
-   A copy of the plug-in is needed if it has been modified or a custom plug-in.
-   If the issue is related to the execution of a plug-in step, collect the following:
    -   Input properties
    -   Output properties
    -   Output log
    -   Error log
-   A copy of any custom post-processing scripts.
-   Screen shots that include the the complete HCL UrbanCode Deploy page

## Troubleshooting server problems

Problems with the HCL UrbanCode Deploy server include HTTP requests that result in errors such as

```
Code 500 Internal Server Error
```

and error messages in the deployserver.out file. In addition to the type of operating system and version, description of what happened and what was being done at the time of the failure, collect the following information:

-   The Java type \(JDK/JRE\), version and update number. There are several ways to gather this information:
    -   Open the installed.properties file in the JVM installation directory. The **install.java.home** property contains the version of the JDK or JRE.
    -   Run the following command:
        -   Unix: install.java.home/java -version
        -   Windows: install.java.home\\java -version 

            Where install.java.home is the Java installation directory.

            **Note:** Running the command with the absolute path is necessary to avoid the system JVM being selected instead of the one configured to run HCL UrbanCode Deploy.

-   If the problem is related to agent connectivity, gather the logs from the following location: ucd\_location/logs/connection/agent-name/\*.
-   If the problem is related to agent auto discovery and configuration include the following:
    -   ucd\_location/logs/autoDiscover/agent-name/\*
    -   ucd\_location/logs/autoConfigure/agent-name/\*
-   If the issue is related to a user application or component process, provide screen captures of the process and the step properties for the steps that are failing.

**Considerations for Version 6.1.0.2 and later** 

If you are using HCL UrbanCode Deploy version 6.1.0.2 and later, you can gather server information using the user interface.

1.  Log into the HCL UrbanCode Deploy server.
2.  Click **Settings** \> **System** \> **Diagnostics \(Download\)** to download the diagnostics bundle.

    The diagnostic bundle includes the following:

    -   All files in the server /bin directory used for debugging configuration
    -   All files in the server /conf directory used for debugging configuration
    -   All files in the server patches directory
    -   All files in the server var/log\[code\] directory
    -   The diagnostics directory, which contains the following:
        -   **latest5000Requests.json**

            Timing and details about the last 5000 REST calls made to the server.

        -   **longestRequestsLast30Days.json**

            Timing and details about the longest requests over the last 30 days.

        -   **recordCounts.json**

            Counts of various types of objects present on the server .


**Considerations for Version 6.1.0.1 and earlier**

If you are using HCL UrbanCode Deploy version 6.1.0.1 and earlier:

-   Collect all the following files located on the HCL UrbanCode Deploy server. The most important file is the deployserver.out file.
    -   bin/set\_env
    -   conf/installed.version
    -   conf/log4j.properties
    -   conf/server/installed.properties 
    -   var/log/deployserver.out
    -   var/log/\*
-   Gather information about patches that have been included. Patches are JAR files containing replacement Java classes for HCL UrbanCode Deploy. The list of patches and the patched Java files can be viewed in the Patches page of the HCL UrbanCode Deploy user interface. To access this page, click **Settings** \> **System** \> **Patches**. When the server starts, it loads the classes in these JAR files before loading those from the server base installation. Multiple patches that overwrite the same file can conflict with each other; there is no clear way to tell which was loaded in this case. Include an archive file containing all the patches on the system and a screen capture of the Patches page.

## Troubleshooting user interface problems

Symptoms of user interface problems include pages not loading, missing pages, and pages with incorrect information. Some user interface issues may be the result of a server problem.

In general, it is useful to identify the REST call that is causing the problem. Use a tool to that gathers timestamps for the HTTP responses and the return code if one was given. This capability is built into some browsers. such as Firebug.

For all user interface related issues, there can never be to many screen captures. Ensure that the screen captures the full screen. Partial screen captures can lack relevant content.

If the browser console is available, provide a screen capture of it. It might contains console errors helpful in troubleshooting.

**Parent topic:** [General product troubleshooting](../topics/c_troubleshooting_and_support_resources.md)

