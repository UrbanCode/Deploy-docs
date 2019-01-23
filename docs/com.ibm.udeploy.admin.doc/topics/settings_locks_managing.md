# Managing locks

A lock ensures that processes do not interfere with one another. Normally, locks are released after they are no longer needed. Sometimes, a lock is not released, and its associated process is unable to complete.The lock management feature helps you to identify and resolve abnormal lock conditions.

Follow these steps to view and resolve locks.

1.  A running process with a lock, like all active processes, is shown on the Dashboard tab with a status of `Running`. If a locked process takes longer to complete than expected, you can cancel the process from the Dashboard, or investigate it fully with the Settings tab.
2.  Display the Locks pane by clicking the **Locks** link on the Settings tab \(**Settings** \> **Locks**\).The Locks pane displays the following information:

    |Field|Description|
    |-----|-----------|
    |Name|The name identifies the lock. The displayed name is a concatenation of the component or application name \(depending on type\) + process name + resource name.|
    |Type|Indicates whether the process that created the lock is a component or application type. Locks can be applied only to component or application processes.|
    |Component/Application|Displays the name of the component or application that contains the lock. Clicking an item displays \(depending on the type\) the Component pane, or Application pane, where you can investigate the lock.|
    |Resource/Environment|Displays the name of the resource or environment that contains the lock. Clicking an item displays \(depending on the type\) the Resource pane, or Environment pane.|
    |Process|Displays the name of the process that contains the lock. Clicking an item displays the process in the process editor.|
    |Actions|Lists the available actions.|

3.  Resolve the lock by selecting an action:

    |Action|Description|
    |------|-----------|
    |View Request|Displays the process log for the process that contains the lock. You can use the **Actions** field on the displayed pane to see the name of the process step that is causing the lock.|
    |Release|Releases the lock, which enables the associated process to continue processing.|

    If the HCL® UrbanCode™ Deploy server and or agents go down while a locked process is running, HCL UrbanCode Deploy automatically restores any interrupted processes along with any locks they might contain after service is restored.


**Parent topic:** [Server settings and configuration](../../com.ibm.udeploy.doc/topics/settings_ch.md)

**Parent topic:** [Managing security](../../com.ibm.udeploy.admin.doc/topics/security_ch.md)

