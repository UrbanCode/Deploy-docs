# Modifying blueprints to access the Chef validator key in version 6.2.1 and later

If you upgrade your blueprint design server to version 6.2.1 or later, you might need to modify references to the Chef validator key before you provision environments from existing blueprints.

In version 6.2.1 of the blueprint design server, the method of providing the Chef validator key changed. Instead of obtaining the key value from an external location during provisioning, the blueprint design server itself provides the key value to the Chef server.

If you used Chef in versions of the blueprint designer before 6.2.1 and upgraded to version 6.2.1 or later, you might need to modify your existing blueprints before you provision an environment from it. For example, if you are using a different Chef server or stopped hosting the key value in an external location, you must make the following changes before you provision.

1.   Add a chef\_validator\_key parameter. The parameter resembles the following code:

    ```
    chef_validator_key:
      type: string
      description: 'The Chef validator private key'
      hidden: true
    ```

2.   In the OS::Heat::SoftwareDeployment resource for each Chef role, replace the CHEF\_VALID\_PEM\_URL input value property with the CHEF\_VALIDATOR\_KEY input value property. The input property must reference the chef\_validator\_key parameter and resembles the following code:

    ```
    Chef_role:
      type: OS::Heat::SoftwareDeployment
      properties:
        config: { get_resource: Chef_role_sw_config }
        server: { get_resource: image }
        input_values:
          **CHEF\_VALIDATOR\_KEY: \{ get\_param: chef\_validator\_key \}**
    ```

3.   In the OS::Heat::SoftwareConfig resource for the Chef roles, replace the CHEF\_VALID\_PEM\_URL input property with the CHEF\_VALIDATOR\_KEY input property. The input property must reference the chef\_validator\_key parameter and resembles the following code:

    ```
    Chef_role_sw_config:
      type: OS::Heat::SoftwareConfig
      properties:
        group: chef
        inputs:
          - name: **CHEF\_VALIDATOR\_KEY**
            type: String
    ```


Provision an environment from the blueprint. See [Provisioning environments from the blueprint designer \(through OpenStack Heat\)](env_provision_edt.md#).

**Note:** Before you provision an environment, you must also upgrade the Chef hook on the images on your cloud. See [Updating Chef-compatible images](cloud_update_chef_images.md#).

**Parent topic:** [Editing blueprints with the blueprint designer](../../com.edt.doc/topics/blueprint_create.md)

