# Creating components from the file system

You can create components by importing artifacts from the file system on the HCL® UrbanCode™ Deploy server. You can import a single version or automatically import versions as they are added to the file system.

HCL UrbanCode Deploy imports local files by two methods:

-   **File System**

    This method imports all files in the specified directory. You can manually update these files to create component versions, but the server does not create versions automatically. See [Creating components from a nonversioned file system](comp_create_filesystem_basic.md).

-   **File System \(Versioned\)**

    This method treats each subdirectory in the target directory as a different version of the artifacts. You can set the server to check for new subdirectories periodically and automatically create component versions when new subdirectories are detected. See [Creating components from a versioned file system](comp_create_filesystem_versioned.md).


In either case, the artifacts must be on the same file system as the HCL UrbanCode Deploy server.

