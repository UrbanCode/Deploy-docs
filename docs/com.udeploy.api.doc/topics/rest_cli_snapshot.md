# snapshot resource

Resources for creating snapshots.

-   **[Add a component version to a snapshot](../../com.udeploy.api.doc/topics/rest_cli_snapshot_addversiontosnapshot_put.md)**  

-   **[Add a status to a snapshot](../../com.udeploy.api.doc/topics/rest_cli_snapshot_addstatustosnapshot_put.md)**  

-   **[Create a snapshot](../../com.udeploy.api.doc/topics/rest_cli_snapshot_createsnapshot_put.md)**  
This command creates a snapshot by specifying the components \(optional\) for the snapshot, rather than taking a snapshot of an environment.
-   **[Delete a snapshot](../../com.udeploy.api.doc/topics/rest_cli_snapshot_deletesnapshot_delete.md)**  

-   **[Get a list of statuses on a snapshot](../../com.udeploy.api.doc/topics/rest_cli_snapshot_getstatuslist_get.md)**  

-   **[Get information about a snapshot](../../com.udeploy.api.doc/topics/rest_cli_snapshot_getsnapshot_get.md)**  

-   **[Get the list of configuration objects in a snapshot](../../com.udeploy.api.doc/topics/rest_cli_snapshot_getsnapshotconfiguration_get.md)**  

-   **[Get the list of versions in a snapshot](../../com.udeploy.api.doc/topics/rest_cli_snapshot_getsnapshotversions_get.md)**  

-   **[Lock a snapshot's configuration](../../com.udeploy.api.doc/topics/rest_cli_snapshot_locksnapshotconfiguration_put.md)**  
This command locks the configuration included in a snapshot. This prevents the snapshot from being affected by any future changes to the relevant configuration and also prevents users from manually changing which configuration the snapshot is using. This cannot be reversed.
-   **[Lock a snapshot's version list](../../com.udeploy.api.doc/topics/rest_cli_snapshot_locksnapshotversions_put.md)**  
This command locks the list of component versions included in a snapshot. This cannot be reversed and prevents any future changes to the list of versions included in the snapshot.
-   **[Remove a component version from a snapshot](../../com.udeploy.api.doc/topics/rest_cli_snapshot_removeversionfromsnapshot_put.md)**  

-   **[Take a snapshot of an environment](../../com.udeploy.api.doc/topics/rest_cli_snapshot_createsnapshotofenvironment_put.md)**  


**Parent topic:** [REST commands for the HCL UrbanCode Deploy server](../../com.udeploy.reference.doc/topics/rest_api_ref_commands.md)

