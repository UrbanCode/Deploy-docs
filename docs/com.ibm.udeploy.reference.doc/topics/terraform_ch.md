# Terraform

HCL® UrbanCode™ Deploy includes a Terraform provider and provisioner to represent artifacts from the HCL UrbanCode Deploy server in a Terraform configuration.

Terraform is a tool for building infrastructure. Configuration files describe this infrastructure to Terraform through resources. Terraform is cloud-agnostic and uses providers to implement the API interactions for these resources.

Terraform also includes provisioners. Provisioners are used to execute scripts on a local or remote machine as part of resource creation or destruction. For example, the remote-exec provisioner command runs a script on a remote machine after it is created.

-   **[Setting up Terraform](../../com.ibm.udeploy.reference.doc/topics/terraform_setup.md)**  
The HCL UrbanCode Deploy extensions for Terraform include both a *provider* and a *provisioner*. The Terraform provider resources support interactions with the HCL UrbanCode Deploy server to manage the lifecycle of tasks, such as environment creation, component mapping, and application process execution. The Terraform provisioner for HCL UrbanCode Deploy automates the installation and configuration of an HCL UrbanCode Deploy agent on new virtual machines, in any cloud, and on multiple operating systems.
-   **[HCL UrbanCode Deploy Terraform provider](../../com.ibm.udeploy.reference.doc/topics/terraform_provider_ref.md)**  
The HCL UrbanCode Deploy provider contains the resources to interact with your HCL UrbanCode Deploy server.
-   **[HCL UrbanCode Deploy Terraform provisioner](../../com.ibm.udeploy.reference.doc/topics/terraform_provisioner_ref.md)**  
The HCL UrbanCode Deploy provisioner installs an HCL UrbanCode Deploy agent on a virtual machine that is created by a Terraform configuration.

**Parent topic:** [Extending product function](../../com.ibm.udeploy.doc/topics/c_node_extending.md)

