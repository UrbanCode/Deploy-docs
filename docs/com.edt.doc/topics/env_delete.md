# Deleting cloud environments

You can delete provisioned cloud environments from the HCL® UrbanCode™ Deploy server or from the blueprint designer.

**Warning:** Deleting a cloud environment deletes the virtual nodes and all of the data on them. In most cases, this action can not be undone.

To delete an environment with the blueprint designer, go to the **Environments** ![](../images/icons/environments.gif) tab and in the **Actions** column, click **Delete**![](../images/icons/delete_environment.gif). The instances on the cloud are deleted and the resources in the resource tree are deleted.

To delete an environment with the server, open the application and next to the environment, click **More** ![](../images/icons/more.gif) and then click **Delete**. In the confirmation window you can specify whether to delete the cloud environment and the attached resources in the resource tree.

If the deletion fails, you might need to delete the cloud environment manually. To do this you can log in to the cloud system directly and delete the environment there. If you are using an OpenStack-based cloud and an engine that you installed with HCL UrbanCode Deploy, you can also use Heat commands to delete the environment. To delete a cloud environment using Heat commands, follow these steps:

**Note:** These steps work only with engines that you installed with HCL UrbanCode Deploy.

1.  Log in to the system that hosts the engine.
2.  Set the system variables that are needed to connect to the cloud. By default, these variables are set in the file /root/clientrc. You can apply the variables by running the command `source /root/clientrc`. You might need to update the variables in this file to work with your cloud installation.
3.  Test that you can connect to the cloud by running the command `heat stack-list`. This command should show the stack \(environment\) that did not delete successfully. If this command returns an error, the variables in the /root/clientrc file are not correct; check their values against the information for your cloud system.
4.  Check for stacks that failed to delete by running the following command:

    ```
    heat stack-list -f stack_status=DELETE_FAILED
    ```

5.  In a stack that failed to delete, check for resources of types that begin with `IBM::UrbanCode` by running the following command, where `stack\_id` is the name of the stack that did not delete:

    ```
    heat resource-list stack\_id
    ```

6.  Log in to the HCL UrbanCode Deploy server and delete the resources that are associated with the environment.
7.  Run the following command, where `stack\_id` is the name or ID of the environment that did not delete:

    ```
    heat stack-delete stack\_id
    ```

8.  If the stack-delete command does not work, use the stack-abandon command:
    1.  On the cloud system console, manually delete the virtual machines in the environment.
    2.  If you are using Chef, delete the node from the Chef server. The node name is the value of the NODE\_NAME property on the IBM::UrbanCode::SoftwareDeploy resource in the blueprint. If this property is not specified in the blueprint, the node name is the host name of the virtual machine.
    3.  Log in to the system that hosts the engine.
    4.  Stop the engine and all OpenStack services.
    5.  In the file /etc/heat/heat.conf, set the property enable\_stack\_abandon to `True`.
    6.  Restart the engine and OpenStack services.
    7.  Delete the stack manually with the following command, where `stack\_id` is the name or ID of the environment that did not delete:

        ```
        heat stack-abandon stack\_id
        ```

9.  If the environment uses Chef, delete the Chef users from the Keystone server. The engine creates these users as part of the Chef deployment.

    1.  Delete the user that is named `stackName-serverResourceName-ID`, where `stackName` is the name of the environment or stack, `serverResourceName` is the name of the server resource in the blueprint, and `ID` is a unique ID for the user.
    2.  Delete the user that is named `stackName-softwareDeploymentResourceName-ID`, where `stackName` is the name of the environment or stack, `softwareDeploymentResourceName` is the name of the software deployment resource in the blueprint, and `ID` is a unique ID for the user.
    For example, for an OpenStack Kilo engine, as in version 6.2.1.1 and later, the following command deletes the user `myEnvironment-server1-12345`:

    ```
    openstack user delete myEnvironment-server1-12345
    ```

    For an OpenStack Juno engine, as in version 6.2.1, use the following command:

    ```
    keystone user-delete myEnvironment-server1-12345
    ```


**Parent topic:** [Provisioning cloud environments](../../com.edt.doc/topics/env_provision_ov.md)

