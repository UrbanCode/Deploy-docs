# Build computer resources

Before you run a mobile application build script on a build computer, you must ensure that the required resources exist on the build computer.

## Workspace resources

The following workspace resources must exist on the build computer:

-   The mobile application project source code that you want to build.
-   The Ant build scripts that direct the build.

Using a Rational® Team Concert™ repository workspace to manage your MobileFirst Platform Foundation project source code and build scripts offers the following advantages:

|Advantage|Description|
|---------|-----------|
|Source control|Changes to source code and build scripts can be requested, developed, reviewed, approved, delivered, and tracked based on the requirements of your development project. Build scripts are living files, just like the source code.|
|Build automation|The Jazz™ Build Engine automatically loads the workspace to build onto the build computer early in the processing of a build request. You can create and use a dedicated build workspace for each build definition. Do not point a build definition directly to a stream or to a workspace that is meant for another purpose. For example, do not point a build definition directly to the personal workspace of a user or a team integration workspace. **Note:** The Jazz Build Engine is a component of the Build System Toolkit; it refers to the process that runs on a build computer and runs Ant scripts.

|

## Static resources

The build administrator must manually install the static resources on each build computer.

**Tip:** Install these resources into the same relative locations on each build computer. You can specify the relative locations within either of the following types of build dependency resources:

-   **Build property files**

    Specify the relative locations of the static resources within the build property files. If you install static resources into different locations on different build computers, a location that is specified within a build property file that works on one build computer might fail on another build computer.

-   **Build definitions within Rational® Team Concert™**

    Specify the relative locations of the static resources within the build definitions in Rational® Team Concert™. If you install static resources into different locations on different build computers, a build definition that works on one build computer might fail on another build computer.


The following static resources must exist on the build computer:

|Static resource|Description|
|---------------|-----------|
|Oracle JDK|Use this JDK for running the Ant scripts and Android SDK tools that are run by the build scripts. Ensure that you install a JDK, not a JRE, because some Ant tasks require Java™ tools that are available only in the JDK.|
|Apache Ant|Use Apache Ant to run the Ant scripts.|
|JAR library files|The following JAR library files provide and enable the MobileFirst Platform Foundation Ant tasks that are used in the build scripts:-   **worklight-ant.jar**

Use the worklight-ant.jar file if you are building applications on the IBM® Worklight® Server Version 6.0. This file is contained in the WorklightServer folder of the IBM® Worklight® Server installation.

-   **worklight-ant-builder.jar**

Use the worklight-ant-builder.jar file if you are building applications on the IBM® Worklight® Server Version 6.1.0. This file is contained in the WorklightServer folder of the IBM® Worklight® Server installation.


**Important:** Ensure that the version of the JAR library file that you use \(worklight-ant.jar or worklight-ant-builder.jar\) matches the version on the target server.

**Tip:** An alternative approach to preinstalling the JAR library files on each build computer is to include them in your build workspace. This approach allows your build definitions and engines to build with different versions of MobileFirst Platform Foundation. This approach also supports the generation of reproducible builds.

The disadvantage of this approach is that the JAR library files can be large. The large file size might affect the performance of builds and build computers.

If you share a build system and build computers across multiple teams, use this alternative approach to manage the JAR library files.

|
|Optional. Dojo Toolkit|Install the Dojo Toolkit on each build computer in the following situations:-   The mobile applications under development use Dojo.
-   The mobile application projects either include the Dojo Toolkit \(in the workspace project\) or access it over a Content Delivery Network.

|

## SDKs

Install one of the following SDKs on each build computer:

|SDK|Description|
|---|-----------|
|Apple Xcode SDK|Install on OS X build computers that run builds to produce iOS IPA applications. For more information about installing the Apple Xcode SDK, see [Getting Started with IBM Worklight Module 02.1 Setting Up Your iOS Development Environment](http://public.dhe.ibm.com/software/mobile-solutions/worklight/docs/v600/01_02_Setting_up_your_iOS_development_environment.pdf).|
|Android SDK|Install on build computers that run builds to produce Android APK applications. For more information about installing the Android SDK, see [Getting Started with IBM Worklight Module 02.2; Setting Up Your Android Development Environment](http://public.dhe.ibm.com/software/mobile-solutions/worklight/docs/v600/01_03_Setting_up_your_Android_development_environment.pdf).|

**Parent topic:** [Building mobile applications](../topics/plugins_worklight_build.md)

**Next topic:** [Build scripts](../topics/plugins_worklight_buildtemplates.md)

