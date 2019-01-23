# Sharing blueprints by using a Git repository

When you work with blueprints, you can organize and share them by using the Git distributed version control system.

Create a blueprint that is stored in a team-based repository. See [Creating files with the blueprint designer](blueprint_edit.md#).

The blueprint design server stores blueprints and configuration files in Git repositories. The blueprint design server creates a Git repository for each team and a clone of that repository for each member of the team. To share blueprints and configuration files with other team members, associate the files with the repository for that team when you create them. Complete your changes to the files in your cloned repository, and then share the files by using Git commands.

You can access the contents of a team-based repository only if you are a member of that team. If you are removed from a team, your clone of the team repository is deleted, along with any changed files that you did not push to the team repository.

1.   To minimize conflicts between the commits that you make and the commits that you download from the repository, sync your workspace with the repository before you change files. 

    1.   Click **Repositories**. The Repositories page opens.
    2.   From the **REPOSITORY** list, select the repository that contains the files. 
    3.   Click **Sync**. The **Sync** command downloads commits by using the fetch command, reorders the commits by using the rebase command, and moves your commits to the repository by using the push command.
    4.   Enter the user name and password that you use to access the blueprint designer, and then click **Submit**. 
    All commits that you loaded are shown in the HISTORY pane.

2.   When your repository is up to date, make changes to blueprints in the blueprint designer as usual. 
3.   After you complete your changes, commit all the files in the working directory to your Git repository. 

    1.   From the **REPOSITORY** list, select the repository that contains the files. 
    2.   In the Working Directory Changes pane, type a commit message in the text box. For example, type Adding second Ubuntu image.
    3.   Click **more**, and then specify names and email addresses for **Author** and **Committer**. 
    4.   Select **Save** to save the author and committer information for future commits. 
    5.   Select **Select All**. 
    6.   Click **Commit**. 
    All files in the working directory are committed to the Git repository. The commit is shown in the OUTGOING pane.


**Parent topic:** [Blueprint storage on the blueprint design server](../../com.ibm.edt.doc/topics/blueprint_storage.md)

