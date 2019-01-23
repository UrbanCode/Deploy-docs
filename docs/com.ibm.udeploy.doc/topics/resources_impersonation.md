# Defining default user impersonation credentials

You can define default user impersonation credentials for a resource.

To access resources on a target system, you might need to access a specific user account on that system. Typically, the required credentials are defined in plug-in steps, but default credentials can be defined on resources. Steps that do not have their own credentials use credentials that are defined on associated resources.

1.  Click **Resources**, and then click the resource's name.
2.   Click the **Configuration** tab that is associated with the resource, not the **Configuration** tab at the top of the page. The resource's Basic Settings page is displayed.
3.  Select the **Default Impersonation** check box.
4.   In the **User** and **Password** fields, enter the target system user name and password that can access the resource. The password is encrypted as it is entered.
5.  In the **Group** field, enter the authentication realm group.
6.  To use the sudo command for impersonation, select the **Use Sudo** check box.If the target system uses a UNIX™ or Linux™ operating system, you can use this option. If the target system uses a Windows™ operating system, this option has no effect.
7.  To always use the credentials that are defined on the resource and override any credentials that are defined in process steps, select the **Always Use Default Impersonation** check box.
8.  Click **Save**.

**Parent topic:** [Resources](../topics/resources_ch.md)

