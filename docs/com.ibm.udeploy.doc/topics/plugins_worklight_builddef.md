# Build definitions

In Rational® Team Concert™, a build definition describes the key components of a build.

The build definition describes the following components:

-   The workspace to process.
-   The Ant scripts and targets to run against the workspace.
-   The schedule for the build.
-   The properties that simplify the configuration of the build.
-   The build engines that can manage build requests for the build definition.

The following sections describe the considerations that apply when you build IBM® MobileFirst Platform Foundation mobile applications.

## Supporting build engines

When you specify a build engine to run build requests for the build definition, ensure that any required SDKs \(such as the Android SDK or Apple Xcode SDK\) are installed and configured on the build engine.

## Properties

You can use properties to customize the build for a specific build definition. For example, you can set properties for the path to the build output or the native SDK.

## Ant build file and targets

In the **Build file** field, use the following value to specify the location of the Ant build script that is loaded with the workspace: `load/${buildLabel}/*project*/*folder*/*script*`

Where:

-   **project**

    The name of the project that contains the build scripts.

-   **folder**

    The name of the folder within the project that contains the build scripts.

-   **script**

    The name of the build script XML file.


**Tip:** If you choose a different relative location for your build script in the workspace, you must change the value of the loadDir property.

In the **Build targets** field, specify any specific targets that you want to run in your build script. By default, build scripts run the all target.

## Ant configuration

Ant configuration includes the following tasks:

-   Select the option to include the Jazz™ build toolkit tasks on the Ant library path.
-   In the **Ant home** field, specify the location on the build computer where Apache Ant is installed.
-   In the **Ant arguments** field, specify the -lib argument that includes the worklight-ant.jar required library on the Ant library path. If you are building applications on the IBM Worklight® Server Version 6.1.0, you can use the worklight-ant-builder.jar file instead of worklight-ant.jar.

    **Important:** Ensure that the version of the JAR library file that you use \(worklight-ant.jar or worklight-ant-builder.jar\) matches the version on the target server.

    Use the following format for the -lib argument: `-lib path\JAR file name` 

    Where:

    -   **path**

        The path to the directory on the build computer that contains the JAR file. The path might be a location on the build computer where the JAR libraries were preinstalled. The path might also point to a location within the loaded workspace if you chose to include the JAR libraries in the build workspace.

    -   **JAR file name**

        The name of the JAR file that is included in the library.

-   In the **Java home** field, specify the location on the build computer where the Oracle JDK is installed.


**Parent topic:** [Rational Team Concert Build](../topics/plugins_worklight_jazzbuild.md)

