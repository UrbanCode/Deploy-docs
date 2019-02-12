# Blueprint storage on the blueprint design server

You store blueprints and configuration files that you create with the blueprint designer in Git repositories. By storing blueprints and configurations in the Git repository for a team, you can share the files with members of that team.

Git is a distributed version control system, and OpenStack Heat template blueprints and configuration files are stored in Git repositories. You can store files in three kinds of repositories:

-   The default Git repository
-   A team-based repository on the local Git server, which is on the same computer as your blueprint design server
-   An external Git repository

By default, blueprint and configuration files are stored in a repository that is named default, and only the user that creates the files can access them.

**Note:** If you used a version of the blueprint designer, formerly IBM® UrbanCode™ Deploy with Patterns, earlier than version 6.1.1, you must move your existing blueprints and configuration files to the default repository. See [Moving blueprints and configuration files](../../com.udeploy.install.doc/topics/migrate_ov.md).

In addition to the default repository, the blueprint design server creates a repository on the local Git server for each team. When you create blueprints in the team's repository, all members of the team can access those files. If the team name does not contain spaces, then the Git repository name is the team name. If the team name contains spaces, then the Git repository name contains dash characters \(-\) in place of the spaces.

In addition to using the default and team-based repositories that the blueprint design server creates, you can also use an external Git repository. You can clone your repository and access it from within the blueprint designer. From the **Repositories** list, click **Clone Repository**, and then specify a URL. You can work with Git repositories that a system administrator sets up or with repositories on the web such as IBM Bluemix® DevOps Services. For example, connect to a Git repository on IBM Bluemix DevOps Services by specifying a URL that is similar to https://hub.jazz.net/git/user\_name/project\_name.

If items are stored in the default repository, when you open a blueprint or configuration file in the blueprint designer, you always see the most recent version of that file. Saving a blueprint or configuration file updates the version in the Git repository automatically. No steps are necessary to store changes in the repository or retrieve updates from the repository.

If items are stored in a team-based or external repository, you modify the items in an individual clone of that repository and push completed changes to the shared repository. When you open a blueprint or configuration file in the blueprint designer, you might not see the most recent version of that file. You must manipulate the files by using Git functions, such as commit, fetch, and push, to share your changes and view the changes others make. All Git functions that are available in the blueprint design server are displayed on the Repositories page. You can access the contents of a team-based repository only if you are a member of that team. If you are removed from a team, your clone of the team repository is deleted, along with any changed files that you did not push to the team repository.

-   **[Sharing blueprints by using a Git repository](../../com.edt.doc/topics/blueprint_org.md)**  
When you work with blueprints, you can organize and share them by using the Git distributed version control system.
-   **[Modifying file indexing](../../com.edt.doc/topics/blueprint_index.md)**  
You can index the blueprint and configuration files that you store in the default and team-based Git repositories for your blueprint designer.

**Parent topic:** [Modeling environments for clouds through OpenStack Heat](../../com.edt.doc/topics/blueprint_edit_clouds.md)

