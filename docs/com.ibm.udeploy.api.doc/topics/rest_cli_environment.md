# environment resource

Resources for creating, editing, and provisioning environments.

-   **[Add a base resource to an environment](../../com.ibm.udeploy.api.doc/topics/rest_cli_environment_addbaseresource_put.md)**  

-   **[Add an environment to a team](../../com.ibm.udeploy.api.doc/topics/rest_cli_environment_teams_put.md)**  

-   **[Create a new environment](../../com.ibm.udeploy.api.doc/topics/rest_cli_environment_createenvironment_put.md)**  

-   **[Create a new environment from template](../../com.ibm.udeploy.api.doc/topics/rest_cli_environment_createenvironmentfromtemplate_put.md)**  
This command creates and Environment from a template and attaches it to the specified application.
-   **[Delete all redundant versions for a component in an environment](../../com.ibm.udeploy.api.doc/topics/rest_cli_envid_redundantversions_componentid_delete.md)**  
A version is considered redundant if all of its files have been replaced by versions that have been deployed more recently to the same environment.
-   **[Delete all versions for a component in an environment](../../com.ibm.udeploy.api.doc/topics/rest_cli_envid_versions_componentid_delete.md)**  

-   **[Delete an environment](../../com.ibm.udeploy.api.doc/topics/rest_cli_environment_deleteenvironment_delete.md)**  

-   **[Get all artifacts overlapped in the given version](../../com.ibm.udeploy.api.doc/topics/rest_cli_envid_componentid_resourceid_overlappingartifacts_versionid_get.md)**  
Get all artifacts that are overlapped by later versions. A version is considered safe to rollback if it does not contain overlapping artifacts. It is risky to roll back a version if that version contains overlapping artifacts. This command applies only to z/OS component versions.
-   **[Get all base resources for an environment](../../com.ibm.udeploy.api.doc/topics/rest_cli_environment_getbaseresources_get.md)**  
This command returns a listing of all resources added as base resources to an environment.
-   **[Get component environment properties for an environment](../../com.ibm.udeploy.api.doc/topics/rest_cli_environment_componentproperties_get.md)**  
These properties are defined on the component and their values are set on the environment.
-   **[Get environment property values](../../com.ibm.udeploy.api.doc/topics/rest_cli_environment_getproperties_get.md)**  

-   **[Get information about an environment](../../com.ibm.udeploy.api.doc/topics/rest_cli_environment_info_get.md)**  
This command returns a JSON representation of an environment.
-   **[Get the latest snapshot deployed to an environment](../../com.ibm.udeploy.api.doc/topics/rest_cli_env_snapshot_get.md)**  

-   **[Get the value of a custom property on an environment.](../../com.ibm.udeploy.api.doc/topics/rest_cli_environment_getproperty_get.md)**  

-   **[Provision a cloud environment](../../com.ibm.udeploy.api.doc/topics/rest_cli_environment_provisionenvironment_put.md)**  
This command provisions an instance of an application blueprint and creates an application environment based on that blueprint.
-   **[Remove a base resource from an environment](../../com.ibm.udeploy.api.doc/topics/rest_cli_environment_removebaseresource_put.md)**  

-   **[Remove an environment from a team](../../com.ibm.udeploy.api.doc/topics/rest_cli_environment_teams_delete.md)**  

-   **[Set a component environment property value](../../com.ibm.udeploy.api.doc/topics/rest_cli_environment_componentproperties_put.md)**  
This command will set a component property value specifically for this environment.
-   **[Set a property on environment](../../com.ibm.udeploy.api.doc/topics/rest_cli_environment_propvalue_put.md)**  


**Parent topic:** [REST commands for the HCL UrbanCode Deploy server](../../com.ibm.udeploy.reference.doc/topics/rest_api_ref_commands.md)

