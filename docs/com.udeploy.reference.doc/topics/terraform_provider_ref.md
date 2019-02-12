# HCL UrbanCode Deploy Terraform provider

The HCL® UrbanCode™ Deploy provider contains the resources to interact with your HCL UrbanCode Deploy server.

## Argument reference

|Name|Required|Descriptions|
|----|--------|------------|
|username|True|The HCL UrbanCode Deploy user name.|
|password|True|The HCL UrbanCode Deploy password.|
|ucd\_server\_url|True|The HCL UrbanCode Deploy server URL.|
|proxy\_url|False|The proxy server URL that is used to connect to an HCL UrbanCode Deploy server.|

## Example usage

```
provider "ucd" {
     username = "admin"
     password = "admin_password"
     ucd_server_url = "https://ucd-server.raleigh.ibm.com:8443"
 }
```

## Resources

-   **ucd\_agent\_mapping**: Add an agent to the resource tree.

    |Name|Required|Description|
    |----|--------|-----------|
    |agent\_name|True|The HCL UrbanCode Deploy agent name.|
    |description|False|The description for the agent.|
    |dynamic|False|Determines if the agent is added as a dynamic group.|
    |parent\_id|True|The ID of the resource in the resource tree where the agent is added. This is normally the base resource group ID.|

    **Example usage**

    ```
    resource "ucd_agent_mapping" "agent_resource" {
         agent_name = "database_server_agent"
         description = "Agent to manage the database server"
         parent_id = "${ucd_resource_tree.tree.id}"
     }
    ```

-   **ucd\_application\_process\_request**: Run an application process on an environment.

    |Name|Required|Description|
    |----|--------|-----------|
    |application|True|The application name.|
    |application\_process|True|The application process.|
    |environment|True|The environment name.|
    |properties|False|The JSON string that represents properties.|
    |snapshot|True|The application snapshot.|

    **Example usage**

    ```
    resource "ucd_application_process_request" "application_process_request" {
         application = "JKE"
         application_process = "install"
         environment = "${ucd_environment.environment.name}"
         snapshot = "snapshot_v1"
     }
    ```

-   **ucd\_component\_mapping**: Add a component to the resource tree.

    |Name|Required|Description|
    |----|--------|-----------|
    |component|True|The component name.|
    |description|False|The component description.|
    |parent\_id|True|The ID of the resource in the resource tree under which to place this component. This is normally the agent.|
    |role\_id|False|The component role ID.|
    |role\_properties|False|The component role properties.|
    |use\_impersonation|False|Determines whether or not to use default impersonation.|

    **Example usage**

    ```
    resource "ucd_component_mapping" "jke_resource" {
         component = "jke.war"
         description = "The JKE component"
         parent_id = ""${ucd_agent.agent.id}"
     }
    ```

-   **ucd\_component\_process\_request**: Run a component process on an environment.

    |Name|Required|Description|
    |----|--------|-----------|
    |application|True|The application name.|
    |component |True|The component name.|
    |environment |True|The environment name.|
    |process |True|The component process to run.|
    |resource |True|The ID of the component resource in the resource tree.|
    |sleep\_delay|False|The amount of time to wait between checks for component process completion. The default is 10 seconds.|
    |timeout |False|The amount of time to wait for the component process to complete. The default is 300 seconds.|
    |version |True|The component version.|

    **Example usage**

    ```
    resource "ucd_component_process_request" "component_process_request" {
         application = "JKE"
         component = "jke.war"
         environment = "${ucd_environment.environment.name}"
         process = "deploy"
         resource = "${ucd_component_mapping.component_resource.id}"
         version = "4.0"
     }
    ```

-   **ucd\_environment**: Add an environment to the resource tree.

    |Name|Required|Description|
    |----|--------|-----------|
    |application|True|The application name or ID for the environment.|
    |base\_resource\_group|True|The base resource group name or ID to add to the environment.|
    |color|False|The color for the environment.|
    |component\_property|False|Sets a component environment property. Can be specified multiple times for each property.|
    |delete\_attached\_resources|False|Determines whether or not to delete the resources attached to this environments. The default value is true.|
    |description|False|A description for the environment.|
    |exempt\_process|False|The process exempt from approval.|
    |inherit\_system\_cleanup|False|Determines if the environment uses the component version cleanup settings for the system or component settings.|
    |lock\_snapshots|False|All of the snapshots used in a request to the deployment are locked to prevent changes.|
    |name|True|The environment name.|
    |require\_approvals|False|Determines if the environment requires approvals for deployment.|

    **Example usage**

    ```
    resource "ucd_environment" "environment" {
        name = "my_environment"
        application = "JKE"
        base_resource_group ="${ucd_resource_tree.tree.id}"
        component_property {
           component = "jke.war"
           name = "JKE_DB_HOST"
           value = "${aws_instance.db.private_ip}"
        }
     }
    ```

-    **ucd\_resource\_tree**: Create a top-level resource group.

    |Name|Required|Description|
    |----|--------|-----------|
    |base\_resource\_group\_name|True|The base resource group name.|
    |description|False|A description for the base resource group.|
    |dynamic|False|Determines if the resource group is added as a dynamic group.|

    **Example usage**

    ```
    resource "ucd_resource_tree" "tree" {
        base_resource_group_name = "my_tree"
     }
    ```


**Parent topic:** [Terraform](../../com.udeploy.reference.doc/topics/terraform_ch.md)

