# Estimating the cost for cloud environments

You can specify cost centers for cloud systems and for HCL® UrbanCode™ Deploy components. Then, the blueprint design server estimates the cost of new environments by using that information.

To configure the blueprint design server to estimate the cost of environments, add cost centers for the cloud systems that you are provisioning. If you are deploying HCL UrbanCode Deploy components that have costs, you can also add cost centers for components. Then, when you provision an environment from the blueprint design server as described in [Provisioning environments from the blueprint designer \(through OpenStack Heat\)](../../com.edt.doc/topics/env_provision_edt.md), the blueprint design server estimates the cost of the new environment, which is based on the cost centers.

**Note:** You cannot estimate the cost for cloud environments that you provisioned by using a composite blueprint.

-   **[Importing cost information from clouds](../../com.edt.doc/topics/cost_center_import.md)**  
You can import cost information from clouds to populate cost centers. Importing cost information in this way retrieves information about the prices of cloud resources.
-   **[Specifying costs for cloud resources manually](../../com.edt.doc/topics/cost_center_clouds.md)**  
To estimate the cost of your environments, you can specify information about the prices that your cloud system charges for specific resources.
-   **[Specifying costs for HCL UrbanCode Deploy components](../../com.edt.doc/topics/cost_center_components.md)**  
If components have a cost to deploy, you can assign a cost to them. Then, when you provision an environment, the blueprint design server includes the cost of the components in the cost estimate for the environment.

**Parent topic:** [Configuring](../topics/c_node_configuring.md)

