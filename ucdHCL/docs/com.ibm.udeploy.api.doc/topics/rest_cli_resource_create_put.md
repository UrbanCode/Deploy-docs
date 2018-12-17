# Create a resource

## Request

```
PUT https://{hostname}:{port}
    /cli/resource/create
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "agent": "Name or ID of an agent to use for automation 
  (Optional)",
  "agentPool": "Name or ID of an agent pool to use for 
  automation (Optional)",
  "componentTag": "Name or ID of a component tag to 
  associate with the resource; any components with that tag 
  can be deployed to this resource (Optional)",
  "description": "Description",
  "impersonationForce": "Specify true to prevent children 
  or steps from specifying their own impersonation settings 
  (Optional)",
  "impersonationGroup": "Group for default impersonation 
  (Optional)",
  "impersonationPassword": "Password for default 
  impersonation (Optional)",
  "impersonationUseSudo": "Specify true to use the sudo 
  command for impersonation (Optional)",
  "impersonationUser": "User name for default 
  impersonation (Optional)",
  "name": "Name for the new resource; leave blank to 
  inherit the name from an agent, pool, or role",
  "parent": "ID or path to parent resource; leave blank to 
  create a root resource (Optional)",
  "role": "Name or ID of a resource role to associate with 
  the agent; if this resource is for a component, specify 
  the component name (Optional)",
  "roleProperties": {"Property name": "Property value 
  (Optional)"}
}

```

## Example JSON requests

This JSON request creates a new top-level resource:

```
{
  "name": "My new resource",
  "description": "New resource for command example"
}
```

This JSON request creates a resource group within an existing resource tree:

```
{
  "name": "New child resource",
  "description": "New resource for command example",
  "parent": "/TopLevelResource/subgroup"
}
```

This JSON request creates a component resource. In this case, the parent resource must be an agent resource.

```
{
    "name":"ComponentA",
    "role":"ComponentA",
    "description": "Description of ComponentA",
    "roleProperties": {"MyProp":"Value1"},
    "parent": "/TopLevelResource/agent1",
    "impersonationUser":"user1",
    "impersonationGroup":"group1",
    "impersonationPassword":"password",
    "impersonationUseSudo":false,
    "impersonationForce":true

}
```

This JSON request creates an agent resource. In this case, the agentID parameter is the ID of an agent.

```
{
  "agentId": "0ac81f92-aeb9-34ce-a6c5-93b6aed380f5",
  "name": "agent1",
  "parent": "/agents"
}
```

## Example response

```
{
  "id": "6a2b106b-ce03-44cd-88db-b89de202013c",
  "name": "My new resource",
  "path": "/My new resource",
  "active": true,
  "description": "New resource for command example",
  "inheritTeam": false,
  "impersonationPassword": "****",
  "impersonationUseSudo": false,
  "impersonationForce": false,
  "hasAgent": false,
  "tags": [
  ]
}
```

Related CLI command: [createResource](udclient_createresource.md).

**Note:** Resource Name character limit is 255.

**Parent topic:** [resource resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_resource.md)

