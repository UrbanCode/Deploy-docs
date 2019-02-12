# Migrating data from versions before 6.1.1

Upgrade the server, agents, and agent relays before upgrading the IBM® z/OS® deployment tools.

If you have version data and deployment results that were created by a version of the z/OS agent and deployment tools before version 6.1.1, complete these migration steps.

1.   Determine the repository directory and deployment base directory in the current installation of the product. The repository directory is the value of the ucd.repository property in the profile data set. The location of the profile data set is recorded in the ISPF.conf file. The deployment base directory is typically set in the deploy.base.path environment property. 
2.   Install a new agent or upgrade the current agent. Then, copy files to the new repository and deployment directories. 
    -   For version 6.2.4, the repository directory and the deploy directory are as follows:

-   agent install dir/var/repository
-   agent install dir/var/deploy
    -   For versions from 6.1.1 to 6.2.3, you can find the the repository directory and the deployment directory locations in the profile data set.
3.   Verify the migration by deploying a current version of a component, and then by rolling back version. 

**Parent topic:** [Upgrading IBM z/OS agents](../../com.udeploy.install.doc/topics/upgrade_zOS_agents.md)

**Parent topic:** [Upgrading IBM z/OS agents](../../com.udeploy.install.doc/topics/upgrade_zOS_agents.md)

