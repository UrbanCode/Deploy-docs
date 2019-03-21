# Creating blueprints for cloud environments that use virtual system patterns

Blueprints for clouds that use virtual system patterns \(VSPs\) map the components of an application to the agents on the virtual images in the VSP.

1.   On the HCL® UrbanCode™ Deploy server, click **Applications**, click your application, and then click **Blueprints**. 
2.   Click **Create Blueprint**. 
3.   Specify a name for the blueprint and select the resource template. 
4.   Click **Save**. The new blueprint opens, showing the contents of the template, including the agent prototypes.
5.   Map the components of the application to the agent prototypes: 

    1.   Hover the mouse over an agent prototype and then click **Actions** \> **Add Component**. 
    2.   In the window that opens, select a component, specify its information, and click **Save**. 
    3.   Repeat this process to add the application components to the agent prototypes. Depending on how your application is organized, you can add the same component to multiple agent prototypes or multiple components to the same agent prototype.
    **Note:** If you create an environment from this blueprint and then add component mappings to the blueprint, the component mappings are also added to the environment. However, if you remove component mappings from the blueprint, the component mappings are not removed from the environment.


The complete application blueprint shows how the components are mapped to the agent prototypes. The following example shows a simple blueprint. The resource template contains two agent prototypes. In the blueprint, one component is mapped to each agent prototype.

![A simple blueprint that was created from a two-node resource template](../images/app_blueprint_create_a.gif)

Provision environments from this blueprint. See [Provisioning environments through the server \(through virtual system patterns\)](env_provision_vsp.md).

