# getComponentEnvironmentProperties

Get component environment properties for an environment

These properties are defined on the component and their values are set on the environment.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getComponentEnvironmentProperties [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|environment|string|true|Name or ID of the environment|
|application|string|false|Name or ID of the application; this value is required if you specify the environment name instead of ID|
|component|string|true|Name or ID of the component|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getComponentEnvironmentProperties
  -component JPetStore-APP
  -environment 1f97af86-cde3-4ba2-803b-0e4580dcc05b
```

## Example response

```
[
  {
    "id": "c598738e-2057-44d7-aee7-e805df40cc69",
    "name": "Environment property 1",
    "value": "false",
    "description": "",
    "secure": false
  }
]
```

Related REST command: [Get component environment properties for an environment](rest_cli_environment_componentproperties_get.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

