# Setting up access to clouds in the blueprint designer

You can provide users of the blueprint designer the permissions to access clouds in two ways. You can provide functional IDs through cloud projects, or you can use accounts on an OpenStack cloud that already have permissions.

If you are using an OpenStack cloud, the easiest way to set up access to the cloud is to use that cloud's Keystone identity service for authentication. In this case, users log in to the blueprint design server with the same credentials that they use on the cloud. This method works only for OpenStack clouds. To provide access to a cloud through user accounts on an OpenStack Keystone service, follow these steps:

1.  In the blueprint designer, create an authentication realm for the OpenStack cloud. See [Creating OpenStack identity service authentication realms for the blueprint designer](security_realms_openstack.md).
2.  Import the users from the authentication realm. The blueprint design server creates a cloud connection that is based on this authentication realm and cloud projects that are based on the tenants or projects on the cloud.

    **Note:** To import users, you must log in as a user that was granted the Admin role.

3.  Connect to a cloud. See [Connecting to clouds through the blueprint designer](../../com.edt.doc/topics/security_cloud_connection.md).
4.  Add cloud projects to teams.

If you are not using an OpenStack cloud, or if you do not want to use the accounts on a Keystone identity service, you must create functional IDs and give users access to clouds through those IDs. The functional IDs are represented on the blueprint design server as cloud projects. To provide access to a cloud through functional IDs, follow these steps:

1.  Connect to a cloud. See [Connecting to clouds through the blueprint designer](../../com.edt.doc/topics/security_cloud_connection.md).
2.  On the cloud system, create one or more accounts. The blueprint designer users use these functional IDs to access the cloud.
3.  Add these functional IDs to the cloud connection as cloud projects.
4.  Assign the cloud projects to teams.
5.  Import users from authentication realms or manually add users to the internal authentication realm.
6.  Assign users to roles on the teams.

