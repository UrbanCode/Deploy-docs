# Creating a key file for Google Cloud Platform

To connect the blueprint designer to Google Cloud Platform, you must create an API key file for your service account.

Create an account and project on Google Cloud Platform.

1.  Log in to the Google Cloud Platform dashboard.
2.  From the Google Cloud Platform console, select your project.
3.  Expand the menu by **Google Cloud Platform**, and click **IAM & Admin**.
4.  Click **Service accounts**.You must connect a service account to the blueprint designer so it can make API calls to Google Cloud. See [Using OAuth 2.0 for Server to Server Applications](https://developers.google.com/identity/protocols/OAuth2ServiceAccount).
5.  If you do not have a service account for your project, create one.To provision environments from the blueprint designer, the service account must be assigned the Project Owner, Project Editor, or all Compute Engine roles.
    1.  Click **CREATE SERVICE ACCOUNT**.
    2.  In the Create service account window, type a service account name.
    3.  From the **Role** list, select an appropriate role or set of roles: 
        1.  To grant full access to the project, click **Project** \> **Owner**.
        2.  To grant edit access to the project, click **Project** \> **Editor**
        3.  To grant full access to the Compute Engine roles, click **Compute Engine**, and then click every role in this category.
    4.  Click **CREATE** and then click **CLOSE**.
6.  Generate an API key file.

    1.  From the menu near your service account's name, click **Create key**.
    2.  In the Create private key for "your\_service\_account" window, ensure that **JSON** is selected.
    3.  Click **CREATE** and then click **CLOSE**.
    The key file is downloaded to your system.


After you create an API key file for your Google Cloud project's service account, you can connect the blueprint designer to it. See [Connecting the blueprint design server to Google Cloud Platform](cloud_connect_google_cloud_server.md#).

**Parent topic:** [Connecting to Google Cloud Platform](../../com.ibm.edt.doc/topics/cloud_connect_google_cloud.md)

