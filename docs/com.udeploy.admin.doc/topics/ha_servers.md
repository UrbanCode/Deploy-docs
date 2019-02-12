# High-availability server processes

While high-availability servers complete the same processes as standalone servers, they run slightly differently and access files in run slightly different locations than individual servers do.

In a high-availability topology, all servers use the same database and a common network storage. The server log and CodeStation repository are stored in the common network storage. Most configuration information and runtime data is stored in the shared database. Each server maintains some independent configuration information, such as the connection information for the database and for JMS.

Because the servers share the database, all servers run on the same interval.

Many activities run the same on high-availability servers as on a standalone server. Some activities run slightly differently:

## Importing component versions \(CodeStation\)

In a clustered high-availability configuration, any server can start the process that imports a component version. If components are configured for automatic imports, all servers poll for component version changes, but they are limited to the polling duration in the system settings. To prevent more than one server from importing a component version or checking for new versions, the database handles server synchronization and a server acquires a database lock before importing or polling.

## Notifications

Notifications are handled by the server that runs the process or starts the related event. For more information, see [Creating Notifications in a Notification Scheme](../../com.udeploy.doc/topics/notify_create.md).

## Running processes and handling failures

While processes are running, step failures are shown in the process log as usual. Error handling is the responsibility of the process author; for example, processes can include steps that run when other steps fail, including automatic rollback steps.

When a process is requested, a request is created in the database. Servers poll the database regularly for new process requests. The first server that finds the process request runs the requested process. Due to a limitation on the server, the process can not be transferred to another server in the cluster. Therefore, if the server fails in the middle of running a process, the process fails. The other servers in the high-availability cluster run future processes, but they can not take over processes that the failed server was running.

If an agent relay stops while a connected agent is running a process, the agent uses its failover settings to connect to other servers or agent relays. If the agent exhausts its failover options, it continues trying to reconnect. If an agent relay or server comes back online, the agent continues to run the process.

Step failures do not cause agents themselves to fail. If an agent stops while it is running a process, the server assumes that the agent is still running the process and does not mark the process as failed.

**Parent topic:** [High availability overview](../../com.udeploy.doc/topics/ha_overview.md)

**Parent topic:** [Managing security](../../com.udeploy.admin.doc/topics/security_ch.md)

