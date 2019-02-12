# Modifying file indexing

You can index the blueprint and configuration files that you store in the default and team-based Git repositories for your blueprint designer.

In version 6.2.1.1 and later of the HCL® UrbanCode™ Deploy blueprint designer, the blueprint design server automatically indexes the blueprints and configuration files that are stored in the default and team-based Git repositories. These files all use the `.yml` or `.yaml` file extensions. You can modify the indexing frequency or disable indexing.

1.   Stop the blueprint design server. See [Starting the blueprint designer, cloud discovery service, and engine](../../com.udeploy.install.doc/topics/start_patterns.md#).
2.   Open the server\_installation\_directory/conf/server/server.properties file. 
3.   Set the indexing behavior of your blueprint design server. By default, the lucene.allowIndexing parameter is set to true. To deactivate indexing, set the lucene.allowIndexing parameter to false.
4.   Set the indexing frequency of your blueprint design server. If you set the lucene.allowIndexing to true, enter the interval in minutes to index the files. By default, the lucene.frequency parameter is set to 2. Frequently indexing the contents of your Git repositories might impact blueprint designer performance.
5.   Save your changes to the /conf/server/server.properties file. 
6.   Restart the blueprint design server. See [Stopping the blueprint designer, cloud discovery service, and engine](../../com.udeploy.install.doc/topics/stop_patterns.md).

**Parent topic:** [Blueprint storage on the blueprint design server](../../com.edt.doc/topics/blueprint_storage.md)

