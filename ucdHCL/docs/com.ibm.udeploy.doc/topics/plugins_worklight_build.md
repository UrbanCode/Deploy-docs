# Building mobile applications

To set up a continuous integration and delivery cycle for your mobile applications, you must build the mobile application artifacts before you deploy them to the IBM® MobileFirst Platform Foundation Server. TheRational® solution for Collaborative Lifecycle Management, MobileFirst Platform Foundation, and HCL® UrbanCode™ Deploy products integrate to help automate the build and deployment of mobile applications.

TheRational solution for Collaborative Lifecycle Management contains the IBM Rational Team Concert™ product that is delivered as an application together with aJazz™ Team Server. Rational Team Concert™ and the Build System Toolkit work together to build your mobile applications. When Rational Team Concert™ is installed on the Jazz™ Team Server, it manages the workspaces, projects, source files, and builds of your mobile applications. The Build System Toolkit runs the actual build tasks.

1.  [Build computer resources](../topics/plugins_worklight_buildresources.md)  
Before you run a mobile application build script on a build computer, you must ensure that the required resources exist on the build computer.
2.  [Build scripts](../topics/plugins_worklight_buildtemplates.md)  
You can create Ant build scripts for MobileFirst Platform Foundation projects that contain applications and adapters. By using these build scripts, you can automate your mobile application builds.
3.  [Rational Team Concert Build](../topics/plugins_worklight_jazzbuild.md)  
The Rational Team Concert™ Build system defines resources that are used to describe and manage builds.

**Parent topic:** [Building and deploying mobile applications](../topics/plugins_worklight_buildanddeploy.md)

