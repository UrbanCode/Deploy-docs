# Creating files with the blueprint designer

You can create blueprints, configuration files, text files, binary files, and folders in the blueprint designer.

-   Connect the blueprint design server to a cloud system. See [Connecting to clouds through the blueprint designer](security_cloud_connection.md).
-   Make sure that your user account is authenticated to a cloud system. See [Setting up access to clouds in the blueprint designer](../../com.ibm.udeploy.admin.doc/topics/security_auth_bds.md).
-   Connect the blueprint design server to the server. See [Connecting the blueprint design server to the server](../../com.ibm.udeploy.doc/topics/ucdp_integrate.md).
-   Log in to the blueprint designer.
-   At the top of the page, select the cloud project and region to use.

1.   Click **Blueprints**. 
2.   Click **New**. 
3.   In the **Type** list, select the file type. The following file types are available:
    -   Select **Folder** to create an internal folder for an existing repository.
    -   Select **Blueprint** to create a file that defines a cloud environment and its components.
    -   Select **Configuration** for your cloud type to define a file that defines properties and values that a blueprint requires to provision an environment to that cloud. See [Editing configuration files](blueprint_configs.md#).
    -   Select **Text File** to create a text file that is used in or by a blueprint. Text files might contain Heat property values that are accessed by using the following format: `property\_name: { get_file: filepath }`.
    -   Select **Binary File** to create a file that contains a script that can be run by the blueprint. The binary files are accessed by using the following format: `property\_name: { get_file: filepath }`.
4.   In the Add a New window, specify a name for the file. 

    **Note:** You must use a unique name. If your blueprint name contains the same sequence of alphanumeric characters with different capitalization as an existing blueprint, only one blueprint will be available to provision from the HCL® UrbanCode™ Deploy server.

5.   To set the repository in which the file is saved, select a project from the **Repository** list. The repository list contains the default project and a project for each team. Each project except the default project corresponds to both a team and a Git repository of the same name. The default project is not associated with a team, and files that are associated with the default project cannot be shared with other users.
6.   To set the folder in which the file is saved, select the folder name from the **Folder** list. 
7.   To copy the contents of an existing source, click **Clone**. If you selected an existing file, you can create a copy of that file. You can also import the contents of a file from your file system or paste the contents into the new file.
8.   Add a description of the file. 
9.   For only binary files, click **Choose File** to select the binary file to import. 
10.  Click **Save**. 

To open a file, go to the **Blueprints** page, and in the **Files** list, click the file.

If you created a blueprint, you can work with it in the diagram editor or the source-code editor. You can also add configuration files to provide different sets of parameter values for different situations.

**Note:** You can also clone a repository and access it from within the blueprint designer. From the **Repositories** list, click **Clone Repository**, and then specify a URL.

**Parent topic:** [Editing blueprints with the blueprint designer](../../com.ibm.edt.doc/topics/blueprint_create.md)

