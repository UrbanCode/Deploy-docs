# Changing or updating the JRE of servers

You can change the JRE of active servers by editing their configuration files.

The new JRE must be from the same vendor as the current JRE.

**Important:** Beginning in version 6.2.2, the HCL® UrbanCode™ Deploy server and agent relays require a Java™ Runtime Environment \(JRE\) or Java Development Kit \(JDK\) version 8.

1.   Install the new JRE. 
2.   Stop the server. 
3.   Update the location of the JRE in the following files: 

    -   In the file server\_install/bin/set\_env, set the value of the JAVA\_HOME system variable to the location of the JRE.
    -   In the file server\_install/conf/server/installed.properties, set the value of the install.java.home property to the location of the JRE.
    **Note:** As a shortcut, you can delete the old JRE and move the new JRE into the location of the old JRE. In this case, you do not need to update the JAVA\_HOME system variable and install.java.home property because they now point to the new JRE.

    **Note:** The value of the JAVA\_HOME system variable must match the value of the install.java.home property.

4.   If the server is running as a service on Windows:™ 
    1.   Open the file server\_install\\bin\\service\\\_service.cmd in a text editor. 
    2.   Edit the line that starts with the code `set JAVA_HOME` to the path to the new JRE. 
    3.   Open a command prompt as an administrator. 
    4.   Go to the server\_install\\bin\\service folder. 
    5.   Remove the service by running the following command: 

        ```
        service.cmd remove service\_name
        ```

        Use the name of the service for `service\_name`. To find the service name, open the services view and find the entry that starts with `HCL UrbanCode Deploy`. The service name is in parentheses in this entry.

    6.   Reinstall the service by running the following command: 

        ```
        service.cmd install service\_name
        ```

5.   Start the server. 

**Parent topic:** [Server settings and configuration](../topics/settings_ch.md)

