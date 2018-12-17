# Permissions reference for using application templates

Permissions for roles that create applications from templates.

Application templates can contain information about the components and environments that are initially available to applications that are created from the templates. The composition of the application template determines which role permissions are needed to create an application from a template.

**Note:** The role permissions in the following tables are only the permissions that are required to create the application from a template. More permissions are necessary to add elements to an application, run processes, or complete a deployment.

To create an application from a template, the user's role must have the following minimum permissions.

**Note:** The user cannot select components or create environments for the application.

|Product area|Permissions|Subpermissions|
|------------|-----------|--------------|
|Application| -   **View Applications**

 |Edit-   **Edit Basic Settings**
-   **Manage Properties**
-   **Manage Teams**

Create-   **Create Applications From Template**

|
|Application Template| -   **View Application Templates**

 | |
|Resource| -   **Create Resources**

 |Edit-   **Manage Teams**

|

To assign existing components to an application from the application template wizard, the user's role must also have the following permissions.

**Note:** To create an application from the application template wizard, the user's role must also have the permissions that are listed in Table 1.

|Product area|Permissions|Subpermissions|
|------------|-----------|--------------|
|Application| |Edit-   **Manage Components**

|
|Component| -   **View Components**

 | |

To create environments for an application from the application template wizard, the user's role must also have the following permissions. To map resources to the environments from the application wizard, the role must also have the permissions in Table 2.

**Note:** To create an application from the application template wizard, the user's role must also have the permissions that are listed in Table 1.

|Product area|Permissions|Subpermissions|
|------------|-----------|--------------|
|Agent| -   **View Agents**

 | |
|Application| |Edit-   **Manage Approvals**
-   **Manage Environments**

|
|Environment| -   **View Environments**

 |Edit-   **Edit Basic Settings**
-   **Manage Base Resources**
-   **Manage Properties**

Create-   **Create Environments From Template**

|
|Environment Template| -   **View Environment Templates**

 | |
|Resource| -   **View Resources**

 |Edit-   **Manage Children**
-   **Map to Environments**
-   **Manage Teams**

|
|Resource Template| -   **View Resource Templates**

 | |

**Parent topic:** [Roles and permissions](../../com.ibm.udeploy.admin.doc/topics/security_roles.md)

