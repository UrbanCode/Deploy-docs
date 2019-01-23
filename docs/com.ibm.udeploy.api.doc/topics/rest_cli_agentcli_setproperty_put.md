# Set a property on a agent

## Request

```
PUT https://{hostname}:{port}
    /cli/agentCLI/setProperty
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "agent": "Name or ID of the agent",
  "isSecure": "Whether the property is secure; the default 
  is the current state of the property, or false if the 
  property is not yet specified (optional)",
  "name": "Name of the property",
  "value": "New value for the property (optional)"
}

```

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/agentCLI/setProperty
  ?agent=myAgent&name=newProperty&value=newValue" -X PUT
```

## Example response

```
{
  "id":"cdf5e901-f19a-48b8-82fc-c92c256e31df",
  "name":"newProperty",
  "value":"newValue",
  "secure":false
}
```

Related CLI command: [setAgentProperty](udclient_setagentproperty.md).

**Parent topic:** [agentCLI resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_agentcli.md)

