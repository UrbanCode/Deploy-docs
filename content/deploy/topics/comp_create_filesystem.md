# Creating components from the file system {#comp_create_filesystem .task}

You can create components by importing artifacts from the file system on the IBM® UrbanCode® Deploy server. You can import a single version or automatically import versions as they are added to the file system.

IBM UrbanCode Deploy imports local files by two methods:

 File System
 :   This method imports all files in the specified directory. You can manually update these files to create component versions, but the server does not create versions automatically. See [Creating components from a nonversioned file system](comp_create_filesystem_basic.md).

  File System \(Versioned\)
 :   This method treats each subdirectory in the target directory as a different version of the artifacts. You can set the server to check for new subdirectories periodically and automatically create component versions when new subdirectories are detected. See [Creating components from a versioned file system](comp_create_filesystem_versioned.md).

 In either case, the artifacts must be on the same file system as the IBM UrbanCode Deploy server.

-   **[Creating components from a nonversioned file system](../topics/comp_create_filesystem_basic.md)**  
To import artifacts that are not stored in versioned folders, store the artifacts in a folder and create a component with the **File System** source configuration type.
-   **[Creating components from a versioned file system](../topics/comp_create_filesystem_versioned.md)**  
To import artifacts with versions, create a directory with subdirectories that represent the versions of the artifacts. Then, create the component with the **File System \(Versioned\)** source configuration type.

**Parent topic:** [Creating components](../topics/comp_create.md)

