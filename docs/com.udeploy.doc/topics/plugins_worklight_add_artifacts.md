# Adding mobile artifacts to HCL UrbanCode Deploy

You can use the build scripts to add your build artifacts to HCL® UrbanCode™ Deploy for deployment to the IBM® MobileFirst Platform Foundation Server.

1.  You can use any of the following methods to add your build artifacts to HCL UrbanCode Deploy: 

        |**Copy the files into a user-defined file system**|Copy the build artifacts to a location on the HCL UrbanCode Deploy server's file system for a versioned file.|
    |**Push the files to the HCL UrbanCode Deploy server**|Use the command-line client \(CLI\) to push the build artifacts to the HCL UrbanCode Deploy server. The CLI is a command-line interface that provides access to the HCL UrbanCode Deploy server. You can use the CLI to push the build artifacts to the HCL UrbanCode Deploy server in the following scenarios:

    -   When the Jazz™ Build Engine and the HCL UrbanCode Deploy server are not installed on the same build computer.
    -   To support running the HCL UrbanCode Deploy server on different operating systems.
**Tip:** You can use the [createVersion](../../com.udeploy.api.doc/topics/udclient_createversion.md) and [addVersionFiles](../../com.udeploy.api.doc/topics/udclient_addversionfiles.md) commands to deploy binary files to the HCL UrbanCode Deploy server.

|
    |**Copy the files into a source-code management system**|Copy the build artifacts into a source-code management system, such as:    -   Git
    -   IBM Rational® Asset Manager
    -   Subversion
|

    **Tip:** Assign a version to the mobile application that is deployed to the Application Center. This version must match the version that is assigned in HCL UrbanCode Deploy.


**Parent topic:** [Building and deploying mobile applications](../topics/plugins_worklight_buildanddeploy.md)

