# Rational Team Concert Build

The Rational Team Concert™ Build system defines resources that are used to describe and manage builds.

The Rational Team Concert Build system in IBM® Rational® Team Concert™ defines the following types of logical resources that are used to describe and manage builds:

-   **Build definition**

    A build definition describes:

    -   The workspace to process.
    -   The Ant scripts and targets to run against the workspace.
    -   The schedule for the build.
    -   The properties to simplify the configuration of the build.
    -   The build engines that can handle build requests for the build definition.
-   **Build engine**

    A build engine represents a Build System Toolkit Jazz™ Build Engine running on a designated build computer. A Jazz™ Build Engine running on a build computer correlates itself to a build engine in Rational® Team Concert™ by specifying the unique identifier of the build engine.

-   **Build request**

    A build request represents a scheduled or explicitly issued request to run a build according to a specified build definition. Build definitions are submitted to a build queue. A Jazz™ Build Engine receives and processes the build request if its corresponding build engine in Rational® Team Concert™ is listed as a supporting build engine for the build definition.

-   **Build result**

    A build result represents the output of a build.


-   **[Build System Toolkit](../topics/plugins_worklight_buildtoolkit.md)**  
Each build computer contains an installation of the Rational Team Concert Build System Toolkit.
-   **[Build definitions](../topics/plugins_worklight_builddef.md)**  
In Rational Team Concert, a build definition describes the key components of a build.

**Parent topic:** [Building mobile applications](../topics/plugins_worklight_build.md)

**Previous topic:** [Build scripts](../topics/plugins_worklight_buildtemplates.md)

