# Modifying the context root of the server

After you install the server, you can modify the context root, if your server configuration requires it.

1.  Stop the server.
2.  From the server installation directory, rename the directory server\_install/opt/tomcat/webapps/ROOT to a new name, such as server\_install/opt/tomcat/webapps/deploy Use the server installation directory for `server\_install`. The default server installation directory is /opt/ucd/server on Linux™ and C:\\Program Files\\ucd\\server on Windows™. 
3.  Make a backup copy of the file opt/tomcat/conf/server.xml. 
4.  Open the file opt/tomcat/conf/server.xml in a text editor
5.  In the server.xml file, find the following line of code:

    ```
    <Context path=""
      docBase="ROOT"
      debug="0"
      reloadable="false"
      useHttpOnly="true"
      sessionCookieName="JSESSIONID_8080">
    ```

6.  In this code, change both the docBase attribute and the path attribute to the name of the new folder.For example, if you renamed the ROOT folder to deploy, the code looks like the following example:

    ```
    <Context path="deploy"
      docBase="deploy"
      debug="0"
      reloadable="false"
      useHttpOnly="true"
      sessionCookieName="JSESSIONID_8080">
    ```

7.  Save the file.
8.  Restart the server.

Now you can access the server at the following URL:

```
https://hostname:port/foldername
```

Use the new name of the folder as `foldername`.

**Parent topic:** [Server settings and configuration](../topics/settings_ch.md)

