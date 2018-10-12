# General information to collect {#troubleshoot_infocollect .concept}

Different issues require different set of information to diagnose and solve problems. However, there is a set of general information used to diagnosis all issues.

When contacting IBM Software Support for assistance with resolving product issues, having topology, product components and version, and time zone information available is helpful.

## Topology { .section}

It is important that the support representative understands the server topology. You should be able to provide enough information that a graph can be sketched representing the topology. Answers to the following questions provide information about the topology.

-   What topology do you use, such as: core, multi-region, high-availability clustered, Blueprint design topology? For information about the types of topologies, see the [Systems and topology overview](ov_systems.md) topic.
-   Do you use a single-server or high-availability topology?
-   What configuration do you use for high-availability, cold-standby or active-active?
-   How do you load-balance the topology? Which protocol and scheduling scheme are used?

## Product components and versions { .section}

Clarify the core product components and their version. For details about the IBM UrbanCode Deploy topology components, see [Systems and topology overview](ov_systems.md).

-   The version of the IBM UrbanCode Deploy server can be found in the deploy-server/conf/installed.version file in the **installed.version** property.
-   Provide the database product and version being used. If the problem is a performance issue, know the number of allowed parallel connections and active locks. For localization issues, knowing how strings are compared is relevant.

It is important to understand the network components between different components involved in issues. Because networks might not be reachable, have different latencies, have restrictive firewall rules, load balancers, proxies, single sign-on solutions, and more; it is important to understand the network between different components involved in issues.

-   Browser and the IBM UrbanCode Deploy server
-   IBM UrbanCode Deploy server and agents or the relay
-   IBM UrbanCode Deploy and the database
-   IBM UrbanCode Deploy agent and source configuration from which you import
-   IBM UrbanCode Deploy client or IBM UrbanCode Deploy post-build publisher
-   IBM UrbanCode Deploy Jenkins publisher and server

## Time zones { .section}

In a globalized work environment, the various product components and users might be located in different time zones creating log data for the issue to have different timestamps. For example, an user reports a problem with times from their time zone, the server writes the time to the log files in its time zone, and the agent on which step runs is in a different time zone.

## Sending data to IBM Support { .section}

The data you collect needs to be in a format that IBM Support specialists can use. The following table outlines the data type and the format for sending to IBM Support.

|Data Type|File Type|
|---------|---------|
|Documents|PDF|
|Logs|Plain text|
|Compressed files|ZIP, TAR, GZ, TAR.GZ,.BZ2|
|Images|PNG, JPG|

**Parent topic:** [General product troubleshooting](../topics/c_troubleshooting_and_support_resources.md)

