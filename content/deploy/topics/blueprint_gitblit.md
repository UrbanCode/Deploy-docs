# Changing the local Git server password {#blueprint_gitblit .task}

To improve the security of your local Git repository, change the default password.

1.   Access the local Git server management page from your web browser. The URL for the Git server management page is derived from the URL for your blueprint designer and is listed on the **System Settings** tab. If you access your blueprint designer from `https://blueprint_designer.my_company:8443/landscaper`, then you access your local Git server management page from `https://blueprint_designer.my_company:8443/gitblit`.

    **Note:** If you cannot access the local Git server, then restart the blueprint design server. If you installed the blueprint design server on AIX® or z/OS®, you must restart the blueprint design server to access the local Git server.

2.   Enter the local Git server user name and password, and click **login**. By default, both the user name and password are gitadmin.
3.   Click the user icon, and select **change password** from the list. 
4.   Enter the new password in both the **password** and **confirm password** fields, and click **save**. 
5.   Return to the blueprint design server, and log in as a user who has the Admin role. 
6.   Click **Settings** \> **System Settings**. 
7.   In the **Password** field of the Local Git Server section, enter the new password. 
8.   Click **Save**. 

