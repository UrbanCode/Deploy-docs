# Configuring blueprint design server teams

In the blueprint designer, teams map users to roles. Teams also include a list of resources that the team owns and cloud projects that the team can use.

Set up the users for the team in the blueprint designer and the roles to assign to those users.

To set up a team, you specify the members of the team, including users and groups. Then, you assign roles to the users and groups to specify their permissions. The blueprint design server creates a repository for the team on the local Git server that team members can use to share blueprints and configuration files.

You can also set resource access for the team which limits the cloud resources team members can use in the blueprint designer palette, when provisioning images, and in the REST API.

**Note:** The teams for the blueprint design server are separate from the teams for the server.

1.   In the blueprint designer, click **Settings** \> **Teams**. 
2.   Select a team or click **Create New Team** to create a new team. 
3.   On the **Members** tab, use the **Add User** or **Add Group** lists to add users and groups to the team. You can filter users by selecting an authentication realm in the **Realm** list.
4.   Assign roles to the users and groups: 
    1.   In the **Members** list, select a user or group. 
    2.   Under **Roles**, select the roles for that user or group. 
5.   Give the team access to cloud projects that contain resources it can access: 

    1.   Go to the **Cloud Authorization** tab. 
    2.   Click **Add**. 
    3.   Select the cloud projects for the team and then click **OK**. 
        -   To apply a filter to the list of clouds, enter text in the field and press Enter.
        -   To grant access to all available clouds, select the check box by the field.
    The team can access all of the resource types for all of regions that are defined by this cloud project.

6.   For each cloud project, set the resource access. The resource access limits the resources that are available in the blueprint designer palette, when provisioning images, and in the REST API.
    1.   From the **Authorization** list, select a cloud project. 
    2.   From the **Region** and **Resource Type** lists, select the region and resource type to set access to. 
    3.   Select the resources that the team can access. To search for a specific resource by name, click **Show Filters**, enter the resource name, and press Enter.
    4.   In this way, set the resource access for each region and resource type. 
7.   Click **Save**. 

Now the users can work with all of the resources that they have access to. The roles that you selected for the users determine what the users can do with those resources. If you assigned cloud projects to the team, the users can use the functional IDs in those projects to deploy cloud instances. A clone of the team-based Git repository is created for each team member, and team members can change the shared files.

