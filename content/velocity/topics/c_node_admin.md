# Administration {#c_node_admin .concept}

A default UrbanCode Velocity administrator ID is included as part of UrbanCode™ Velocity. It is used to install and complete initial configuration tasks.

The UrbanCode Velocity administrator can perform the following tasks from the administrator user interface:

-   Integrations
-   User authentication
-   Environment mapping
-   Line of business mapping

Users who are part of the UrbanCode Deploy system team can perform the following tasks:

-   Environment mapping
-   Line of business mapping

## Security considerations { .section}

To ensure user data security, specify a **logout url** when authenticating users. This ensures that the user is logged out of the system and prevents another person to access their account through the cached browser data.

-   **[Managing integrations](../topics/c_node_integrations.md)**  
Using UrbanCode Velocity you can run deployments and request reports based on your criterion from data retrieved from your UrbanCode Deploy environment. In addition, you can use data from other external tools, such as Jenkins, ServiceNow, and the IBM Cloud DevOps Insights service.
-   **[Configuring an email server](../topics/t_admin_emailServer.md)**  
Configure an email server.
-   **[Setting up the calendar](../topics/t_admin_calendar.md)**  
Use the Calendar Settings page to manage the appearance of calendar events.
-   **[Security](../topics/c_node_security.md)**  
The UrbanCode Velocity security model is organization- and team-based. The organization is the base element; teams belong to organizations. Team members manage releases, events, and deployments. Administrators manage teams and assign users to them.

