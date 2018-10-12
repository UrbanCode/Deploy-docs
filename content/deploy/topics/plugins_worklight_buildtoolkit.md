# Build System Toolkit {#plugins_worklight_buildtoolkit .concept}

Each build computer contains an installation of the Rational® Team Concert® Build System Toolkit.

The Build System Toolkit consists of the following major components:

 Jazz™ Build Engine
 :   The Jazz Build Engine is a command-line tool that polls for and processes build requests from Rational Team Concert. When the Jazz Build Engine is started, it must identify a corresponding build engine in Rational Team Concert. TheJazz Build Engine can then accept any build request whose build definition is supported by the build engine. The Jazz Build Engine runs the Ant script and targets that are specified in the build definition. Each build is represented in Rational Team Concert by a build result.

  Build toolkit
 :   The build toolkit is a collection of Ant tasks. Ant scripts can use these tasks to send information \(such as build progress, results, links, artifacts\) to Rational Team Concert to include in the build result.

  Build agent
 :   The build agent is a lightweight process that handles agent-based builds that support z/OS® or IBM® i build scenarios. For the IBM MobileFirst Platform Foundation \(Worklight®\) plug-in, use the Jazz Build Engine instead.

    **Note:** The Jazz Build Engine is a component of the Build System Toolkit; it refers to the process that runs on a build computer and runs Ant scripts.

 **Parent topic:** [Rational Team Concert Build](../topics/plugins_worklight_jazzbuild.md)

