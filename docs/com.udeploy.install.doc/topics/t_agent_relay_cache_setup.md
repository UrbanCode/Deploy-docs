# Caching artifacts on agent relays

Agent relays can cache downloaded artifacts. Caching artifacts in this way improves performance because agents retrieve artifacts from agent relays instead of from the server.

When you enable artifact caching on an agent relay, the agent relay maintains a local CodeStation repository. This repository stores cached versions of artifacts that are on the server CodeStation repository. By default, the first time an agent requests an artifact, the agent relay retrieves the artifact, caches it in its CodeStation repository, and provides it to the agent. The next time an agent requests the artifact, the relay checks if the cached artifact is up to date. Then, the agent relay updates the cached artifact if necessary and provides the artifact to the agent.

By default, agent relays cache only artifacts that one or more agents request. You can also configure agent relays to pre-populate the cache with all artifacts with a specified status. In this case, the agent relays populate the cache with artifacts that have the specified status. Then, the artifacts are available immediately when agents request them.

Caching artifacts improves performance if the server is a long distance from the agents. In this case, caching artifacts on an agent relay that is close to the agents reduces the time that it takes to copy artifacts to the agents. Caching artifacts also improves performance if many agents retrieve artifacts from the server at the same time. In this case, caching the artifacts transfers server load to the agent relays.

**Note:** By default, each hour, the agent relay checks the size of the artifact cache. If the cache is over the limit, the agent relay removes files based on which files have not been used in the longest time. Therefore, the total disk space used by the cache can exceed the cache limit. You must ensure that the agent relay has enough space to store all of the cached artifacts.

**Note:** If you cache files on the relay, do not put the CodeStation cache on an NFS file system.

To pre-cache artifacts on agent relays, set up one or more component version statuses. Component versions with these statuses are cached on agent relays before agents request the component versions.

If you did not configure agent relay artifact caching when you installed the agent relay, you can also configure it by modifying its properties.

1.   Open the /agent-relay-install/conf/agentrelay.properties file. 
2.   Control caching with the `agentrelay.codestation.enable_replication` property: 
    -   To enable caching, set the property to `TRUE`. An example true property resembles this code: `agentrelay.codestation.enable_replication=true`.
    -   To disable caching set the property to `FALSE`. An example false property resembles this code: `agentrelay.codestation.enable_replication=false`.

        **Note:** If caching is enabled on an agent relay and disabled later, the cached artifacts are not deleted. To delete the artifacts manually, stop the agent relay and then delete the folders /agent-relay-install/var/repository/ptr and /agent-relay-install/var/repository/blob.

3.   To preload artifact versions that contain certain statuses, specify the statuses in the `agentrelay.codestation.geotags` property. Separate statuses with commas. If you edit a status that contains a comma, the comma must be escaped. A modified `agentrelay.codestation.geotags` property might resemble the following code: `agentrelay.codestation.geotags=Hello%2c World,Production`

    Then, ensure that the component versions that you want to cache have one of these statuses.

4.   Modify the cache size with the `agentrelay.codestation.max_cache_size` property. You can specify a number of bytes, or use the extensions "`K`," "`M`," "`G`," or "`T`" to indicate kilobytes, megabytes, gigabytes, and terabytes. For example, to specify 5 gigabytes, type `5G`. 

**Parent topic:** [Agents and agent relay configuration](../../com.udeploy.doc/topics/configure_agents.md)

