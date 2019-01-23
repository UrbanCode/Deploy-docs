# getEnvironmentProperties

Get environment property values

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  getEnvironmentProperties [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|environment|string|true|Name or ID of the environment|
|application|string|false|Name or ID of the application; this value is required if you specify the environment name instead of ID|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getEnvironmentProperties 
  -application JPetStore 
  -environment "Tutorial environment 1"
```

## Example response

```
[
  {
    "id": "9dbcf2f6-a96e-4ee5-ba65-07c5fa8422c9",
    "name": "db.url",
    "value": "jdbc:mysql://localhost:3306/jpetstore",
    "description": "",
    "secure": false
  },
  {
    "id": "f395d093-95d8-4d1d-8901-fc0329ef6bdb",
    "name": "tomcat.home",
    "value": "/opt/apache-tomcat-6.0.37",
    "description": "",
    "secure": false
  },
  {
    "id": "404fb6e0-b0a9-433a-9b63-d8614017d459",
    "name": "tomcat.manager.url",
    "value": "http://localhost:8080/manager",
    "description": "",
    "secure": false
  },
  {
    "id": "167fa275-bb95-460b-97b2-e27e713a1400",
    "name": "tomcat.start",
    "value": "/opt/apache-tomcat-6.0.37/bin/startup.sh",
    "description": "",
    "secure": false
  }
]
```

Related REST command: [Get environment property values](rest_cli_environment_getproperties_get.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

