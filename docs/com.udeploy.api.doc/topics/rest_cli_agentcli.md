# agentCLI resource

Resources for creating, editing, and deleting agents.

-   **[Returns a JSONObject with count of agents to status. Expected format: \{ "ONLINE":4, "UPGRADE\_RECOMMENDED":1 \} Requires Settings Tab permission](../../com.udeploy.api.doc/topics/rest_cli_agentcli_statuses_get.md)**  

-   **[Add a tag to an agent](../../com.udeploy.api.doc/topics/rest_cli_agentcli_tag_put.md)**  

-   **[Add an agent to a team](../../com.udeploy.api.doc/topics/rest_cli_agentcli_teams_put.md)**  

-   **[Delete a tag from an agent](../../com.udeploy.api.doc/topics/rest_cli_agentcli_tag_delete.md)**  

-   **[Delete an agent](../../com.udeploy.api.doc/topics/rest_cli_agentcli_delete.md)**  
Agents should be shut down before deletion.
-   **[Get information about all agents](../../com.udeploy.api.doc/topics/rest_cli_agentcli_get.md)**  

-   **[Get information about an agent](../../com.udeploy.api.doc/topics/rest_cli_agentcli_info_get.md)**  
 This command returns a JSON representation of an agent.
-   **[Get the value of a property on an agent](../../com.udeploy.api.doc/topics/rest_cli_agentcli_getproperty_get.md)**  

-   **[List all tags on an agent](../../com.udeploy.api.doc/topics/rest_cli_agentcli_tag_get.md)**  

-   **[Remove a property from an agent](../../com.udeploy.api.doc/topics/rest_cli_agentcli_deleteproperty_put.md)**  

-   **[Remove an agent from a team](../../com.udeploy.api.doc/topics/rest_cli_agentcli_teams_delete.md)**  

-   **[Rename an agent](../../com.udeploy.api.doc/topics/rest_cli_agentcli_rename_put.md)**  
 Rename an agent. Use this command if running the agent configuration script in the agent bin directory is not convenient. Only the administrator can run this method.
-   **[Restart an agent](../../com.udeploy.api.doc/topics/rest_cli_agentcli_restart_put.md)**  

-   **[Return high watermarks for agent usage](../../com.udeploy.api.doc/topics/rest_cli_agentcli_usage_get.md)**  

-   **[Set a property on a agent](../../com.udeploy.api.doc/topics/rest_cli_agentcli_setproperty_put.md)**  

-   **[Shut down an agent](../../com.udeploy.api.doc/topics/rest_cli_agentcli_shutdown_put.md)**  

-   **[Test the connection from an agent to the server](../../com.udeploy.api.doc/topics/rest_cli_agentcli_test_put.md)**  
 The agent's JMS and HTTP connections to the server will be tested.
-   **[Upgrade an agent](../../com.udeploy.api.doc/topics/rest_cli_agentcli_upgrade_put.md)**  
 The agent will be upgraded to the agent version corresponding with the UrbanCode Deploy server version.

**Parent topic:** [REST commands for the HCL UrbanCode Deploy server](../../com.udeploy.reference.doc/topics/rest_api_ref_commands.md)

