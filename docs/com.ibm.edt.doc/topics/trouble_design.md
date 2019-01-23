# Troubleshooting the blueprint design server

If you are having trouble with the blueprint design server, here are some things that might help.

-   **Derby conflict during installation**

    If you install HCL® UrbanCode™ Deploy and the blueprint design server on the same system and use Derby for both systems, you might see this error during the blueprint design server installation:

    ```
    Starting embedded database ...
    Stopping embedded database ...
    [ant:java] : /opt/ibm-ucd-patterns/var/db is not a valid directory
            at org.apache.tools.ant.taskdefs.Java.setupWorkingDir(Java.java:855)
            at org.apache.tools.ant.taskdefs.Java.setupExecutable(Java.java:825)
    ```

    In this case, use a different database for either system; do not use Derby for both HCL® UrbanCode™ Deploy and the blueprint design server.

-   **Palette does not show virtual images**

    If you do not see your virtual images in the palette, make sure that the images are configured properly. For example, Amazon EC2 images must be registered with the cloud discovery service; see [Registering Amazon EC2 images with the cloud discovery service](integrate_ec2_image.md). For all clouds, see [Configuring images for use with the blueprint designer](cloud_connect_vm_requirements.md).

    Make sure that you are connected to the correct cloud project and that you have permission to see the images.

-   ****Files** list does not display folders**

    If you do not see the default or team folders in the **Files** list in the blueprint designer, reset the file storage cache.

    1.  Stop the blueprint design server. See [Stopping the blueprint designer, cloud discovery service, and engine](../../com.ibm.udeploy.install.doc/topics/stop_patterns.md#).
    2.  Remove the cache folder.
        -   On Linux™, delete the /installed\_location/ibm-ucd-patterns/opt/tomcat/work/Catalina/localhost/landscaper/eclipse directory. The installed\_location is the location where you installed the blueprint designer, and the default value is `opt`.
        -   On Windows™, delete the C:/installed\_location/ibm-ucd-patterns/opt/tomcat/work/Catalina/localhost/landscaper/eclipse directory. The installed\_location is the location where you installed the blueprint designer, and the default value is `Program Files`.
    3.  Restart the blueprint design server. See [Starting the blueprint designer, cloud discovery service, and engine](../../com.ibm.udeploy.install.doc/topics/start_patterns.md#).
-   ****Files** list does not display team folders**

    If you do not see the team folders in the **Files** list in the blueprint designer and cannot log into the local Git server, modify the user file for the Git server.

    On the system that hosts the blueprint design server, open the users.conf file in the /installed\_directory/repositories/gitblit/data/ folder. The installed\_directory is the location where you installed the blueprint design server, and the default value is opt/ibm-ucd-patterns. Add the following code to the file:

    ```
    [user "gitadmin"]
     password = password
     role = "#admin"
     role = "#notfederated"
    ```

-   **Check the logs**

    The default location for the blueprint design server logs is /opt/ibm-ucd-patterns/logs.

-   **Increase Hystrix timeout values**

    While you check the logs for problems, you might see timeout errors. For example, in the var/logs/patterns.out file, you might view an error that is similar to this entry:

    ```
    # cat var/logs/patterns.out | grep "Timeout occurred while waiting for a
        response" | cut -d" " -f6- | sort  | uniq -c  | sort -n -r
        6 com.urbancode.landscape.persistence.versionedfs.VFSAbstractCommand -  Timeout occurred while
        waiting for a response from service tier.  Consider increasing timeout for
        VFSListWorkspaces.
        3 com.urbancode.landscape.component.engine.UCLFindAllArtifactsCommand -  Timeout occurred while
        waiting for a response from service tier.  Consider increasing timeout for
        FindAllArtifacts.
    ```

    You can find the following `VFSListWorkspaces`, `FindAllArtifacts`, or `UCDGetAuthTokens` entries in the /opt/ibm-ucd-patterns/conf/server/ folder in one of these properties files:

    -   config.properties
    -   engine-services-client.properties
    -   heat-api-client.properties
    -   versioned-filesystem-client.properties
    Open the ./conf/server/versioned-filesystem-client.properties file, and increase the timeout value from, for example, `5000` to `15000`. Enter the new value in this property:

    ```
    hystrix.command.VFSListWorkspaces.execution.isolation.thread.timeoutInMilliseconds=15000
    ```

    Open the ./conf/server/heat-api-client.properties file, and increase the timeout value from, for example, `10000` to `20000`. Enter the new value in this property:

    ```
    hystrix.command.FindAllArtifacts.execution.isolation.thread.timeoutInMilliseconds=20000
    ```

    Open the ./conf/server/engine-services-client.properties file, and increase the timeout value from, for example, `15000` to `30000`. Enter the new value in this property:

    ```
    hystrix.command.FindAllArtifacts.execution.isolation.thread.timeoutInMilliseconds=30000
    ```

-   **Permissions**

    Ensure that your user account has access to the correct cloud projects and other resources. To use the blueprint designer, a user account must be on a team and, and the account must have a role on that team. The team must have access to a cloud project. See [Configuring security for the blueprint design server](../../com.ibm.udeploy.admin.doc/topics/security_ov.md).

    If your user account is imported from HCL® UrbanCode™ Deploy, the components that you can see in the blueprint editor are limited by your permissions on the blueprint design server.

-   **Check the cloud discovery service**

    The cloud discovery service receives many concurrent requests from the blueprint design server. Each request opens a file on the discovery service. If many users are using the blueprint designer at the same time, the discovery service might reach the open file limit. In this case, the blueprint design server does not respond normally. To resolve the problem, increase the number of files that can be open on the discovery service. On a Linux™ system, increase the `ulimit` value to allow more open files.

    In versions before version 6.1.1.1, the discovery service could be installed automatically as part of an engine or separately from other components of the product. Beginning in version 6.1.1.1, the discovery service is installed as part of the blueprint design server.

-   **Check the DNS access to the blueprint design server host name**

    If your blueprint design server is running on a cloud system that does not provide DNS lookup for host names, the blueprint design server might not function properly. In this case, blueprints do not appear on the dashboard page or in the list of files on the blueprint design server. You might also see errors when you create or update blueprints. In the log, you see errors that say `Timeout occurred while waiting for a response from service tier`.

    To resolve this issue, add a reference that relates the host name to the IP address in the /etc/hosts file on the computer that hosts the blueprint design server.

-   **Indentation problem B**

    Indentation is significant in Heat templates. Therefore, you must keep the indentation consistent throughout the template. To fix this problem, convert spaces to tabs and make sure that each indentation level in the template has the same number of tabs. This error tends to appear when you copy and paste from other editors into the blueprint editor.


-   **Resized virtual machines on VMware did not change size**

    If you change the size of a VMware virtual machine in the blueprint designer, you might need to extend the file system to see the change on the virtual machine. See [Increasing the size of a disk partition](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=1004071).


For more troubleshooting information, see the UrbanCode community on IBM® developerWorks®: [https://developer.ibm.com/answers/?community=urbancode](https://developer.ibm.com/answers/?community=urbancode).

**Parent topic:** [Troubleshooting modeling and provisioning cloud environments](../../com.ibm.udeploy.doc/topics/trouble_blueprints_ov.md)

