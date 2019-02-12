# Setting up Terraform

The HCL® UrbanCode™ Deploy extensions for Terraform include both a *provider* and a *provisioner*. The Terraform provider resources support interactions with the HCL UrbanCode Deploy server to manage the lifecycle of tasks, such as environment creation, component mapping, and application process execution. The Terraform provisioner for HCL UrbanCode Deploy automates the installation and configuration of an HCL UrbanCode Deploy agent on new virtual machines, in any cloud, and on multiple operating systems.

-   Install Terraform from [https://www.terraform.io/downloads.html](https://www.terraform.io/downloads.html). Version 0.10.0 or later is required.
-   If you installed an earlier version of the HCL UrbanCode Deploy extensions for Terraform, do the following steps:
    1.  In your Terraform installation folder, delete the provider and provisioner files.
    2.  Remove the following lines in the ~/.terraformrc file for Unix-like systems and the %APPDATA%/terraform.rc file for Windows:

        ```
        providers {
          ucd = "<path_to_terraform_installation_folder>/terraform-provider-urbancode-deploy"
          ucdagent = "<path_to_terraform_installation_folder>/terraform-provisioner-urbancode-deploy"
        }
        ```


To use the Terraform extensions for HCL UrbanCode Deploy to orchestrate full-stack provisioning of an HCL UrbanCode Deploy application, complete the following setup steps.

1.   Download and extract the installation files for the engine. These files are available for download from the IBM® Passport Advantage® website. See the [IBM UrbanCode Deploy download document](https://www.ibm.com/software/passportadvantage/pao_customer.html). 
2.   Change to the ibm-ucd-patterns-install/engine-install/resources/ibm-ucd-terraform directory. 
3.   Copy the provider and provisioner files for your platform to the Terraform third-party plugins folder. 

    -   On Windows, in the sub-path terraform.d/plugins beneath your user's "Application Data" directory.
    -   On all other systems, in the sub-path .terraform.d/plugins in your user's home directory.
    The `terraform init` script searches this directory for additional plugins during plugin initialization.

    **Note:** The naming scheme for provider plugins is `terraform-provider-NAME-vX.Y.Z`, and Terraform uses the name to understand the name and version of a particular provider binary.

    **Note:** Ensure that the copied files are in an executable format.

4.   Change to the ibm-ucd-terraform/test folder. For example, run this command: 

    ```
    cd <extracted_location>/ibm-ucd-patterns-install/engine-install/resources/ibm-ucd-terraform/test
    ```

5.   Use the sample Terraform configuration to test both the provider and provisioner. 

    1.   Install the AWS and TLS providers: 

        ```
        terraform init
        ```

    2.   Apply the configuration: 

        ```
        terraform apply
        
        ```

    Your HCL UrbanCode Deploy server must be directly accessible from your Terraform runtime server. You are individually prompted for each of these variable values:

    -   AWS Access ID
    -   AWS Secret Key
    -   The name of the AWS Key Pair to create
    -   UrbanCode Deploy Server URL
    -   UrbanCode Deploy User
    -   UrbanCode Deploy Password
6.   To verify the results of the apply, log into your HCL UrbanCode Deploy server, and click **Resources**. In the Resource Tree, expand the **provider-test-base-resource-group** resource group. If the resource group contains an agent, and the agent is online, the apply succeeded. 
7.   Clean up the resources after your test: 

    ```
    terraform destroy
    ```

    All resources should be destroyed. To verify the results, return to your HCL UrbanCode Deploy server, and click **Resources**. The entry for the **provider-test-base-resource-group** resource group is no longer in the resource tree.


**Parent topic:** [Terraform](../../com.udeploy.reference.doc/topics/terraform_ch.md)

