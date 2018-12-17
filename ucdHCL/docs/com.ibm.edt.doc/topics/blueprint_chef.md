# Applying Chef roles to environments

Chef roles describe automation tasks to be run on a target system. You can apply roles to images in a blueprint.

**Note:** These instructions are for using Chef when you provision environments on cloud systems via OpenStack Heat. To use Chef in component processes, see the [Chef automation plugin](https://developer.ibm.com/urbancode/plugin/chef/).

-   Chef roles are supported on only OpenStack, VMware, and SoftLayer® clouds.
-   Connect to a Chef server. See [Integrating with Chef](integrate_chef.md).
-   Configure your images to work with Chef. See [Creating Chef-compatible images](integrate_chef_images.md).
-   Connect the blueprint design server to a cloud system. See [Connecting to clouds through the blueprint designer](security_cloud_connection.md).

When you provision an environment that includes Chef roles, the virtual image contacts the Chef server, downloads the associated roles and cookbooks, and runs the specified automation.

1.  In a blueprint, add one or more images.These images must be configured to work with Chef as described in [Creating Chef-compatible images](integrate_chef_images.md).
2.  From the **Components** palette drawer, drag one or more Chef roles to the images.Two resources are added to the blueprint source code for each Chef role. The `OS::Heat::SoftwareDeployment` resource type represents the deployment instance of the role, and the `OS::Heat::SoftwareConfig` resource type represents the configuration properties for the role, including its inputs and outputs.

    **Note:** When you add a Chef role to an image, the name property is removed from the image. When you use a Chef role on an image, the engine generates a unique name for the image automatically.

3.   Specify the properties for the `OS::Heat::SoftwareDeployment`. 
    -   Set the ENV\_NAME property. This property must have the name of an environment on the Chef server. By default, Chef servers have an environment that is named `_default`. This environment must exist on the Chef server. The blueprint design server does not create environments on the Chef server. Do not confuse Chef environments with cloud environments. For information about Chef environments, see [http://docs.chef.io/environments.html](http://docs.chef.io/environments.html).
    -   Assign the Chef node name.

        If you do not specify a value, the fully qualified host name of the server that you create is the Chef node name.

        -   To manually assign the node name, specify a value in the NODE\_NAME property. Inn in the following code.

            ```
              Chef_tutorial:
                type: OS::Heat::SoftwareDeployment
                properties:
                  config: { get_resource: Chef_tutorial_sw_config }
                  server: { get_resource: rhel-7-chef_image }
                  input_values:
                    CHEF_VALIDATOR_KEY: { get_param: chef_validator_key }
                    CHEF_SERVER_URL: { get_param: chef_server_url }
                    ENV_NAME: { get_param: chef_env }
                    VALIDATOR_NAME: { get_param: chef_validator_name }
                    RUN_LIST: "role[tutorial]"
                    **NODE\_NAME: Tutorial\_node**
                    CHEF_METADATA:
                  actions:
                    - CREATE
                    - DELETE
            
            ```

        -   To automatically assign the node name based on the stack id, specify a variable in the NODE\_NAME property, as shown in the following code.

            ```
              Chef_tutorial:
                type: OS::Heat::SoftwareDeployment
                properties:
                  config: { get_resource: Chef_tutorial_sw_config }
                  server: { get_resource: rhel-7-chef_image }
                  input_values:
                    CHEF_VALIDATOR_KEY: { get_param: chef_validator_key }
                    CHEF_SERVER_URL: { get_param: chef_server_url }
                    ENV_NAME: { get_param: chef_env }
                    VALIDATOR_NAME: { get_param: chef_validator_name }
                    RUN_LIST: "role[write-file]"
                    **NODE\_NAME: \_node\_name\_string\_**
                    CHEF_METADATA:
                  actions:
                    - CREATE
                    - DELETE
            ```

            You must configure the `OS::Heat::SoftwareConfig` resource to obtain the value for the variable in the NODE\_NAME property. In the following code, the value of the variable `_node_name_string_` is the text test-node- and the value of the OS::stack\_id parameter.

            ```
              Chef_write-file_sw_config:
                type: OS::Heat::SoftwareConfig
                properties:
                  config:
                    str_replace:
                      template: |
                      **params:
                        \_node\_name\_string\_:
                          str\_replace:
                            template: |
                              "test-node-\_res\_id\_"
                            params:
                              \_res\_id\_: \{ get\_param: "OS::stack\_id" \}**
            ```

            The value of the `_node_name_string_` variable resembles the following code:

            ```
            test-node-9f6a4b07-254d-406k-9bdb-fd5f8a576918
            ```

        **Note:** If you place multiple Chef roles on the same instance, set the NODE\_NAME property for only the first role that you run. To specify the deployment order of the roles, see [Deploying components with blueprints](blueprint_deploy_env.md#deployment_order).

    -   Set any metadata for the Chef role in the CHEF\_METADATA section. By providing values in the CHEF\_METADATA property, you can set attributes for the Chef role. For an example of using CHEF\_METADATA, see [Using output properties from a Chef recipe](https://developer.ibm.com/urbancode/docs/using-output-properties-chef-recipe/).
4.   If you used Chef in versions of the blueprint designer before 6.2.1, upgraded to version 6.2.1 or later, and removed the validator key value from a URL that you host, you must modify your blueprint. See [Modifying blueprints to access the Chef validator key in version 6.2.1 and later](chef_validator.md#).
5.   Specify the Chef validator key. 

When you provision environments from this blueprint, the Chef server applies the roles to the environments. If any of the Chef roles fails, the provisioning process fails, in the same way as a step in a process fails.

**Parent topic:** [Modeling environments for clouds through OpenStack Heat](../../com.ibm.edt.doc/topics/blueprint_edit_clouds.md)

