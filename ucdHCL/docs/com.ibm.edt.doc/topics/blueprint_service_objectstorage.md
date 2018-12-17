# Modeling object storage with Amazon S3 and OpenStack Swift

Object storage systems \(such as Amazon Simple Storage Service \(S3\) and OpenStack Swift\) host collections of files and provide them on demand. These collections are sometimes called object storage containers object storage buckets. By including containers in a blueprint, you can provide information about those containers to applications.

In your components, create properties that refer to the location or other details about object storage systems. For example, add component environment properties that refer to the location of the object storage. Then, you can use those properties in component processes. In this way, you provide information about the object storage to the application components.

You can model a new container or an existing container in a blueprint.

The following object storage systems are supported:

-   Amazon Simple Storage Service, which refers to containers as object storage buckets
-   OpenStack Swift, which refers to containers as object storage containers

1.   In the blueprint designer, from the **Storage** drawer, drag the **New Object Storage Bucket** to the blueprint. 
2.  Specify the name for the container or bucket.To create a container, specify a new name in the name property. To refer to an existing container, specify the name of an existing container.
3.  If you are creating a container, specify other properties for the container.If the container exists, these properties are ignored. For example, you can specify the access control for the container with the X-Container-Read and X-Container-Write properties. For example, the following code creates a new container that is named `my_object_storage` and specifies that the users `jsmith` and `jwilson` have read access.

    ```
    my_object_storage:
      type: OS::Swift::Container
      properties:
        name: MyObjectStorage
        X-Container-Read: jsmith, jwilson
    ```

4.   From the **Components** drawer, add one or more components to images in the blueprint. In the blueprint, the component resources have properties that refer to the properties on the HCL® UrbanCode™ Deploy server.
5.  Link the properties in the component to the properties of the container resource.To link a component to the `my_object_storage` container, the code might look like the following example. In this example, the component has a property that is named `StorageContainerURL`. The component uses this property value to access object storage. To provide the value for the property, refer to the matching property on the container resource, as in the following example:

    ```
    MyComponent_sw_config:
      type: IBM::UrbanCode::SoftwareConfig::UCD
      properties: 
        name: "MyComponent"
        component_process: deploy
        application: { get_attr: [resource_tree, application_name] }
        environment_name: { get_attr: [resource_tree, environment_name] }
        inputs:
          **StorageContainerURL : \{ get\_attr: \[my\_object\_storage, WebsiteURL\] \}**
    ```

6.  If you are connecting to an Amazon S3 bucket, create a configuration file and map the `OS::Swift::Container` resource type to the `IBM::S3::Bucket` resource type.

When you provision an environment from this blueprint, the component can access the object storage container.

**Note:** When you delete an environment that contains an object storage container, the container is not deleted.

**Parent topic:** [Modeling software services](../../com.ibm.edt.doc/topics/blueprint_service_ov.md)

