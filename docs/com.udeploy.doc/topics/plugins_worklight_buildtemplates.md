# Build scripts

You can create Ant build scripts for MobileFirst Platform Foundation projects that contain applications and adapters. By using these build scripts, you can automate your mobile application builds.

## Build script tasks

You can create build scripts that use the following types of Ant tasks:

|Type of Ant task|Description|
|----------------|-----------|
|Built in tasks from Apache Ant|Includes tasks such as:-   `<echo>`
-   `<report>`
-   `<mkdir>`
-   `<exec>`
-   `<replaceregexp>`

|
|Tasks from IBM® MobileFirst Platform Foundation|These tasks complete the following actions:-   Build MobileFirst Platform Foundation applications and adapters, such as `<app-builder>` and `<adapter-builder>`. MobileFirst Platform Foundation provides a set of Ant tasks that help you to build adapters and MobileFirst Platform Foundation applications for your MobileFirst Platform Foundation Server.
-   Build MobileFirst Platform Foundation web archive projects. MobileFirst Platform Foundation provides the `<war-builder>` Ant task for building the MobileFirst Platform Foundation project WAR file.

|
|Tasks from the Rational® Team Concert™ Build System Toolkit|The following tasks provide information to the build results:-   `<startBuildActivity>`
-   `<linkPublisher>`
-   `<artifactPublisher>`

|

## Sample build script task flow

You can create build scripts for MobileFirst Platform Foundation projects that contain different numbers of applications or adapters. The following sample task flow describes the overall design of a build script for a MobileFirst Platform Foundation project that has a single MobileFirst Platform Foundation application and a single adapter.

1.  Use Ant `<property>` elements to set the properties.
2.  Use a hybrid target to build MobileFirst Platform Foundation applications, adapters, and MobileFirst Platform Foundation web archive projects. The hybrid target contains the following actions:
    1.  URLs that point to the MobileFirst Platform Foundation Server Console and the Application Center are published to either the Ant build log or the Rational Team Concert™ build results.
    2.  The MobileFirst Platform Foundation `<app-builder>` Ant task builds the MobileFirst Platform Foundation application.
    3.  The resulting .wlapp file is stored in the build output.
    4.  The MobileFirst Platform Foundation `<adapter-builder>` Ant task builds the adapter.
    5.  The resulting .adapter file is stored in the build output.
    6.  The MobileFirst Platform Foundation `<war-builder>` Ant task builds the MobileFirst Platform Foundation web archive project.
    7.  The resulting WAR file is stored in the build output.
    8.  Optional. If you use Rational Team Concert, you can publish the .wlapp, .adapter, and WAR files to the Rational Team Concert build results.
3.  When you build an Android application, include the following actions to build the native Android APK file:
    1.  Run the android command-line tool from the Android SDK to generate the Android build.xml file.
    2.  Run the generated Android build.xml file to build the APK file.
    3.  Optional. Publish the Android APK file to the location where you store your build output. For example, if you use Rational Team Concert, publish the APK file to the Rational Team Concert build results.
4.  When you build an iOS application, include the following actions to build the native iOS IPA file:
    1.  Run the xcodebuild command-line tool from the Xcode SDK to build the iOS application.
    2.  Run the xcrun command-line tools from the Xcode SDK to package the iOS application into an IPA file.
    3.  Optional. Publish the iOS IPA file to the location where you store your build output. For example, if you use Rational Team Concert, publish the IPA file to the Rational Team Concert build results.
5.  Add your MobileFirst Platform Foundation application, adapter, MobileFirst Platform Foundation web archive project \(WAR file\), and native application \(Android APK file or iOS IPA file\) to HCL® UrbanCode™ Deploy as a new version.

    **Tip:** You can have multiple MobileFirst Platform Foundation applications and adapters. If you have more than one MobileFirst Platform Foundation application or adapter, repeat calls to tasks to build the mobile artifacts, add new property values, and then add the new artifacts to HCL UrbanCode Deploy.


**Parent topic:** [Building mobile applications](../topics/plugins_worklight_build.md)

**Previous topic:** [Build computer resources](../topics/plugins_worklight_buildresources.md)

**Next topic:** [Rational Team Concert Build](../topics/plugins_worklight_jazzbuild.md)

