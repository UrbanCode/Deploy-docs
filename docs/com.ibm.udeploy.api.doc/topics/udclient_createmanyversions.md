# createManyVersions

Create multiple component versions

Do not use the keywords latest, latestVersion, or newest as the version name.

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  createManyVersions [JSON file]
```

## Parameters

None.

## Template

This command takes a JSON request string or file. Use the following template for the request:

```
{"wrappedArray": [{
  "componentId": "Component identifier. If not specified 
  componentName is required",
  "componentName": "Component name. If not specified 
  componentId is required",
  "links": [{
    "link": "Link url",
    "name": "Link name"
  }],
  "status": [{"name": "Status name"}],
  "version": "Version name to create"
}]}

```

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  createManyVersions
  newVersions.json
```

## Example JSON request

```
[
  {
    "version": "New version 1",
    "componentName": "MyComponent",
    "links": [
      {
        "name": "New link",
        "link": "http://www.ibm.com"
      }
    ],
    "status": [
      {
        "name": "MyStatus"
      }
    ]
  },
  {
    "version": "New version 2",
    "componentName": "MyComponent",
    "links": [
      {
        "name": "New link",
        "link": "http://www.ibm.com"
      }
    ],
    "status": [
      {
        "name": "MyStatus"
      }
    ]
  }
]
```

Related REST command: [Create multiple component versions](rest_cli_version_createmanyversions_post.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

