# Installing test fixes to the engine

Test fixes are provided by IBM® support to correct specific issues with the Heat orchestration engine. You replace individual files in the directory that contains the installed engine.

Ensure that you installed the correct version of the engine, as listed in the readme file for the test fix.

In most cases, test fixes come with specific instructions. In general, these instructions look like the following steps. However, always use the instructions in the readme file or the instructions that are provided by IBM support.

1.   Log in to the server that hosts the engine as the root user. 
2.   Stop the engine. See [Stopping the blueprint designer, cloud discovery service, and engine](stop_patterns.md#).
3.   Change to the directory that contains the Heat plug-in. 
    -   If you installed an engine that is provided with HCL® UrbanCode™ Deploy, change to the /usr/lib/heat directory.
    -   If you extended an engine, change to the plug-in directory for that engine. The location of the plug-in directory is the value of the plugin\_dirs parameter in the heat.conf file. By default, on a Red Hat Enterprise Linux™ system, the Heat plug-in location is /usr/lib/heat, and on an Ubuntu system, the plug-in location is /usr/local/lib/heat.
4.   Determine the file permissions and file owner of the contents of the Heat plug-in. To obtain this information, you can run the following command:

    ```
    ls -l | grep heat
    ```

    The permissions output resembles the following code:

    ```
    drwxr-xr-x 2 root root 4096 Dec 24 08:49 heat
    ```

    In this case, the file permissions are `drwxr-xr-x`, which has an octal value of 755, and owner of the file is the user `root` in the `root` group.

5.   Download the file or files for the test fix and extract them. 
6.   Change the file permissions and owner of the test fix files to match the values of the existing Heat plug-in files. 

    **Note:** You must use the permission, owner, and group values that you obtained in step [4](#step_3).

    To change the owner and group of the files, run the following command:

    ```
    chown -R user\_name:group\_name /extracted\_fix\_location
    ```

    To change the permissions of the files, run the following command:

    ```
    chmod -R octal\_permissions\_value /extracted\_fix\_location
    ```

    In this command, you must use the octal value of the file permissions, such as 755.

7.   Archive the files that are replaced in the test fix. 
    1.   Locate files in the /usr/lib/heat/ibm-cloud-ext/ directory that contain the same names as the files in the test fix folder. 
    2.   Rename each file that the test fix contains to indicate that it is outdated. For example, if the test fix contains the vra\_server.py file, rename the installed file to vra\_server.py.old.
8.   Copy the test fix files from the archive file to the appropriate folders within the /usr/lib/heat/ibm-cloud-ext/ directory. Ensure that each file is placed in the correct folder. For example, the vra\_server.py file is located in the /usr/lib/heat/ibm-cloud-ext/resources/vra directory.
9.   Start the engine. See [Starting the blueprint designer, cloud discovery service, and engine](start_patterns.md#).

To remove the test fix from the engine, stop the engine, delete the files that you added, and restore the original file names to the replaced files.

**Parent topic:** [Installing the blueprint designer](../../com.edt.doc/topics/install_ch_bpd.md)

