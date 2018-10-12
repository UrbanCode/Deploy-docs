# Integrating with JIRA {#c_integration_jira .task}

Seamlessly incorporate Jira projects into your releases.

In Jira, the **Accept remote API calls** configuration option must be set to **ON**.

Jira integrations are configured on the release level. The first time you configure an integration, you supply connection information to your Jira server, map Jira projects to the issue tracking tool. After an integration is configured, you can reuse it with other releases.

To configure a Jira integration, complete the following steps:

1.   On the Release detail page, click **Release stories**, and then click **Configure story integration**. 
2.   In the Add Integration to Issue Tracking Tool window, specify how issues are found: 
    -   If you want to configure a new integration, select **I have the URL for an issue assigned to the release**, and then complete the following steps:
        1.  Enter the URL of your Jira server, and the Jira user credentials, and then click **Continue**.
        2.  In the Add Integration to Issue Tracking Tool window, click **Add**, and then select the Jira project, field name, and value.
        3.  Click **Continue**.
        4.  If issues are found, click **Save**. Matching Jira issues are imported and displayed on the **Release stories** tab.
    -   If you want to use an existing integration, select **I'll directly enter all the info to connect to my issue tracker**, and click **Continue**. Complete the integration by following step **b.**.

The number of imported issues is displayed in the release status area. To see the release, click **Release stories**. You can use the links on the **Release stories** tab to open the issues in Jira.

**Parent topic:** [Managing integrations](../topics/c_node_integrations.md)

