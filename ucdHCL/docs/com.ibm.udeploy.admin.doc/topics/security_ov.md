# Configuring security for the blueprint design server

The access control settings for the blueprint design server are similar to the settings for the HCL® UrbanCode™ Deploy server. You can create teams and roles, assign users to those teams and roles, and assign resources to those teams.

However, the blueprint design server is different because it does not store its own list of users. Instead, the blueprint design server imports accounts from authentication realms, including OpenStack Keystone services, LDAP servers, and Single Sign-On servers. Therefore, to configure access control, you must first import user accounts from one or more authentication realms, as described in [Setting up access to clouds in the blueprint designer](security_auth_bds.md). Then, you associate those user accounts with roles and teams, as described in [Configuring blueprint design server users](security_users.md), [Configuring blueprint design server user roles](security_roles_bds.md), and [Configuring blueprint design server teams](security_teams_bds.md).

**Note:** These teams and roles are separate from the teams and roles for the HCL UrbanCode Deploy server.

Access control settings include the following concepts:

-   **Users**

    Each user represents an account on the blueprint designer. Users can be members of groups.Rather than having its own list of users, the blueprint design server imports accounts from authentication realms, including OpenStack Keystone services and LDAP servers.

-   **Roles**

    A role is a set of permissions. For example, a role can include the permission to view, create, or edit blueprints. You cannot assign roles directly to users. Instead, you assign the role to a team. Then, the users in the team have the permissions in the role.

-   **Teams**

    Teams associate users with roles. When you assign a user to a team, you must also assign that user to a role.

-   **Groups**

    Groups are collections of users. You can use groups as a shortcut to adding users to teams. Instead of adding users to teams one at a time, you can add a group of users to a team and role. Groups for the internal authentication realm can be manually created. Groups for LDAP realms are automatically created when users are imported. Any groups that the imported users belong to are also imported. Groups for both LDAP and SSO realms are automatically created when each user initially logs in to the blueprint designer.

-   **Authentication realms**

    An authentication realm is a source of information about users. By default, the blueprint design server has an authentication realm that is named Internal Authentication, which includes the administrator and any users that you add to the server manually. You can create other authentication realms to import users from other sources, such as LDAP servers and OpenStack identity service \(Keystone\).

-   **Cloud projects**

    A cloud project includes a functional ID with access to a cloud system. Users can access this cloud project and use that functional ID to request cloud resources.


