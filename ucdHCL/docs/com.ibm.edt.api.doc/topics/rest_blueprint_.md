# rest/blueprint resource

Resources for creating, editing, and deleting blueprints

-   **[Create a blueprint](../../com.ibm.edt.api.doc/topics/rest_blueprint__post.md)**  
This command creates a blueprint from the supplied JSON string.
-   **[Delete a blueprint](../../com.ibm.edt.api.doc/topics/rest_bpid_delete.md)**  

-   **[Estimate the cost for a blueprint in the cloud](../../com.ibm.edt.api.doc/topics/rest_bpid_cost_put.md)**  
This command estimates the running cost of the blueprint in the selected cloud.
-   **[Get a configuration file](../../com.ibm.edt.api.doc/topics/rest_bpid_confid_version_configurationversion_document_get.md)**  
This command returns a JSON representation of a specific version of a configuration file. You specify the configuration file in the Location header.
-   **[Get a specific version of a blueprint](../../com.ibm.edt.api.doc/topics/rest_bpid_version_blueprintversion_document_get.md)**  
The contents of the blueprint can be returned as either plain text or JSON depending on the "Accept" header. By default, JSON is returned.
-   **[Get a unique environment name](../../com.ibm.edt.api.doc/topics/rest_blueprint_environmentname_uniqueenvironmentname__get.md)**  
This command checks that an environment name is not already in use. If the specified name is in use, the command returns a similar unique name.
-   **[Get the contents of a blueprint](../../com.ibm.edt.api.doc/topics/rest_bpid_get.md)**  
This command returns the contents of the blueprint in either plain text or JSON depending on the "Accept" header. By default, it returns plain text.
-   **[List all blueprint resources](../../com.ibm.edt.api.doc/topics/rest_blueprint_resources_get.md)**  
This command returns a list of blueprints.
-   **[List blueprints](../../com.ibm.edt.api.doc/topics/rest_blueprint__get.md)**  
This command lists all blueprints that you have access to.
-   **[List configuration files for a blueprint](../../com.ibm.edt.api.doc/topics/rest_bpid_configuration_get.md)**  

-   **[List configuration files for a blueprint and the specified cloud](../../com.ibm.edt.api.doc/topics/rest_bpid_cloudprojid_configuration_get.md)**  

-   **[List the blueprints that refer to an application](../../com.ibm.edt.api.doc/topics/rest_blueprint__appid_appname_get.md)**  

-   **[List the environments that are provisioned from a blueprint](../../com.ibm.edt.api.doc/topics/rest_bpid_environments__get.md)**  

-   **[List the outputs of a blueprint](../../com.ibm.edt.api.doc/topics/rest_blueprint_outputs_get.md)**  
Use the URL query parameter "t=UC::Blueprint::name" to specify the blueprint. To specify multiple blueprints, separate additional query parameters with an ampersand \(&\).
-   **[List the parameters required to provision a blueprint](../../com.ibm.edt.api.doc/topics/rest_bpid_parameters_get.md)**  

-   **[List the parameters required to provision a blueprint with a configuration and common configuration file](../../com.ibm.edt.api.doc/topics/rest_bpid_confid_common_additionalconfigurationid_parameters_get.md)**  

-   **[List the parameters required to provision a blueprint with a configuration file](../../com.ibm.edt.api.doc/topics/rest_bpid_confid_parameters_get.md)**  

-   **[List the versions of a blueprint](../../com.ibm.edt.api.doc/topics/rest_bpid_version_get.md)**  

-   **[List the versions of a configuration file](../../com.ibm.edt.api.doc/topics/rest_bpid_confid_version_get.md)**  

-   **[Provision a blueprint](../../com.ibm.edt.api.doc/topics/rest_bpid_deploy_put.md)**  
This command provisions a blueprint to the cloud along with the parameters in the submitted JSON string.
-   **[Update a blueprint](../../com.ibm.edt.api.doc/topics/rest_bpid_put.md)**  
This command updates a blueprint from the supplied JSON string. The JSON string must include the contents of the blueprint in the "document" attribute.
-   **[Update an environment](../../com.ibm.edt.api.doc/topics/rest_bpid_envid_put.md)**  
This command updates an environment by applying a blueprint to it.
-   **[Validate a blueprint](../../com.ibm.edt.api.doc/topics/rest_bpid_validate_put.md)**  
This command validates a blueprint with the parameters in a JSON string to ensure that the blueprint will deploy correctly.

**Parent topic:** [REST commands for the blueprint design server](../../com.ibm.udeploy.reference.doc/topics/rest_api_ref_commands_edt.md)

