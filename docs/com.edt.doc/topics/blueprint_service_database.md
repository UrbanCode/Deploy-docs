# Modeling databases with Amazon RDS

Relational database services such as Amazon Relational Database Service \(RDS\) provide cloud-based databases. You can model these databases in blueprints and connect applications to them.

In your components, create properties that refer to the address or other details about the database. For example, add component environment properties that refer to the endpoint location and port of the database. Then, you can use those properties in component processes. In this way, you provide information about the database to the application components so that when the components are installed, they can connect to the database.

You can model a new database or an existing database in a blueprint. Amazon RDS is the only type of database service that is supported.

1.  In the blueprint editor, from the **Services** drawer, drag the **New RDS Instance** to the blueprint to create a database, or drag an existing database to the blueprint. 
2.  If you are creating a database, specify the information about the database, such as the type of database and the size of the instance.The following example shows a database that is named `my_database`:

    ```
    my_database:
      type: IBM::RDS::Instance
      properties:
        name: my_database
        db_instance_class: db.m1.small
        engine: mysql
        engine_version: 5.6.19a
        availability_zone: { get_param: availability_zone }
        master_username: 
        master_password: 
        vpc_security_group_ids: 
        subnet_group:
        parameter_group:
    ```

3.  If you are creating a database, specify the security group for the database by dragging the security group from the **Security** drawer of the palette.The security group controls which Virtual Private Cloud \(VPC\) the database is created in. By default, images can access only databases that are in the same VPC.
4.   From the **Components** drawer, add one or more components to images in the blueprint. In the blueprint, the component resources have properties that refer to the properties on the HCL® UrbanCode™ Deploy server.
5.  Link the properties in the component to the properties of the database.To link a component to the `my_database` database, the code might look like the following example. In this example, the component has properties that are named `ClusterEndpointPort` and `ClusterEndpointAddress`. The component uses these property values to access the database. To provide the property values, refer to the matching property on the database resource, as in this example:

    ```
    databasecomp_sw_config:
      type: IBM::UrbanCode::SoftwareConfig::UCD
      properties: 
        name: "Database-accessing component"
        component_process: deploy
        component_process_timeout: "300"
        ucd_server_url: { get_param: ucd_server_url } # these should come from resource_tree
        ucd_username: { get_param: ucd_user }
        ucd_password: { get_param: ucd_password }
        application: { get_attr: [resource_tree, application_name] }
        environment_name: { get_attr: [resource_tree, environment_name] }
        inputs:
          **endpoint\_port : \{ get\_attr: \[my\_database, endpoint\_address\] \}
          endpoint\_address : \{ get\_attr: \[my\_database, endpoint\_port\] \}**
    ```

6.  Create a configuration file and map the types in the blueprint to the matching Amazon types.

When you provision an environment from this blueprint, the component can access the database.

**Note:** If you provision an environment that contains a new database and then delete the environment, the database is also deleted.

**Parent topic:** [Modeling software services](../../com.edt.doc/topics/blueprint_service_ov.md)

