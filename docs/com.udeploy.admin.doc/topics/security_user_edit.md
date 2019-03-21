# Editing user information manually

You can manually edit the stored name, email address, and password for user accounts on the server for internal security realms. For an SSO authentication realm, name and email address are passed in via HTTP headers \(for example, from an HTTP proxy that is translating Kerberos tokens into HTTP headers\).

Editing user information requires permission to view the **Authentication \(Users\)** page. Make sure that the user's role is assigned to the proper team and **Web UI | Settings Tab** permissions are granted.

1.   On the UrbanCode Deploy main menu bar, click **Settings**. 
2.   To display the authentication page, in the **Security** group, click **Authentication \(Users\)**. 
3.   In the **Actions** column, click **Edit** for the user account that requires updates. 
4.   Edit the **Name** and **Email** fields as needed. When you complete the edits, click **Save**. 
5.   To change the password for a user account, click **Reset Password**, and then enter the new password in the **Password** field. Confirm the new entry in the **Re-enter** field. Click **Save**. 

**Parent topic:** [Authentication realms](../../com.udeploy.admin.doc/topics/security_auth.md)

