# Moving blueprints and configuration files

After you upgrade from a version of the blueprint design server earlier than version 6.1.1, you must move blueprints and configuration files from the file system to the Git repository.

To move the blueprints and configuration files, you must have administrative access to the blueprint designer. Complete the following steps after the blueprint design server is upgraded to version 6.1.1.

When you create blueprints and configuration files in versions of the blueprint designer earlier than version 6.1.1, the blueprints and configuration files are stored on the file system of the blueprint design server, in the workspace folder in the blueprint design server installation directory. After you upgrade to the blueprint design server Version 6.1.1, blueprints and configuration files are stored in Git repositories in the repositories folder in the blueprint design server installation directory. Existing blueprints and configuration files are not available until you move them from the file system to the Git repository.

1.   Log in to the blueprint designer. Log in from the user account that you plan to use to work with the blueprints and configuration files. 
2.  Click **Repositories**.
3.   Click **Repositories** in the list. The repository list opens and No Content is displayed.
4.  Click **Init Repository**, and then type default for the **New folder** name. 
5.   Click **Submit**. The default folder is created in a directory structure under the repositories folder in the blueprint design server installation directory. The exact path is determined by the user name. For a user named user1, the default folder is created in blueprint\_design\_server\_installation\_directory/workspace/repositories/us/user1\_id/OrionContent. The default installation directory is /opt/ibm-ucd-patterns on Linux™ and C:\\Program Files\\ibm-ucd-patterns on Windows™.
6.   Log in to a command line on the computer that is running the blueprint design server. You must log in with administrator privileges.
7.   Copy all files from blueprint\_design\_server\_installation\_directory/workspace to the default folder that you created in step 5. Additionally, ensure that the owner of the files and directories is the root account.

The blueprints and configuration files that were stored in the workspace folder are now available to the user account where you created the default repository.

**Parent topic:** [Upgrading and migrating](../../com.udeploy.doc/topics/c_node_upgrading.md)

