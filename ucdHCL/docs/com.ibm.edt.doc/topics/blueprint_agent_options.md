# Options for deploying agents

Typically, you do not edit the options that are used when HCL® UrbanCode™ Deploy agents are installed on virtual images. However, you can edit the code that is embedded in an agent resource to change how the agent is installed.

When you create a blueprint, the editor adds a resource that represents the HCL UrbanCode Deploy agent, and this resource is installed automatically on each virtual image. The resource is named either `ucd_agent_install_win` or `ucd_agent_install_linux`, depending on the operating system that is installed on the virtual image. The resource includes a call to a script that installs the agent. On Linux™, the install-agent-with-options.sh script is called. On Microsoft™ Windows™, the install-agent-with-options.ps1 script is called. To change how the agent is installed, examine the code in the agent resource and adjust the arguments based on the information in the following table.

|Option name|Command-line parameter|Comments|
|-----------|----------------------|--------|
|Agent name|-n agent\_name|Required. The name of the agent to create.|
|HCL UrbanCode Deploy remote host|-s remote\_host\_URL|Required. The host name of the HCL UrbanCode Deploy server or agent relay to connect to.|
|Agent communication port|-p port\_number|Required. The port number to use for communication with the remote host. By default, the port number is 7918 for HCL UrbanCode Deploy servers and 7916 for agent relays.|
|Start option|-x start\_option|Optional. After installation, starts the agent with the specified options. Valid options are start and run.|
|Use agent relay|-r|Optional. Configures the agent for use with an agent relay.|
|Initial team|-t list\_of\_teams|Optional. A list of team names, separated by commas, to add the agent to when it connects to the server. By default, the initial team is System Team.|
|Proxy host|-k proxy\_host|Optional. The host name of a proxy server to use with an agent relay.|
|Proxy port|-l proxy\_port|Optional. The port of a proxy server to use with an agent relay. By default, the proxy port number is 20080.|
|Disable HTTP failover|-d|Optional. Disables HTTP failover handling for agents that connect through an agent relay.|
|Install service|-v|Optional. This parameter works only on Linux computers. Installs the agent as a service.|
|UCD install location|-c|Optional. Installs HCL UrbanCode Deploy agent to a desired location.|

**Parent topic:** [Blueprint properties, attributes, and parameters](../../com.ibm.udeploy.doc/topics/blueprint_props_ov.md)

