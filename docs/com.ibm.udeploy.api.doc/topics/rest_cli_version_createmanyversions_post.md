# Create multiple component versions

Do not use the keywords latest, latestVersion, or newest as the version name.

## Request

```
POST https://{hostname}:{port}
    /cli/version/createManyVersions

```

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
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/
  version/createManyVersions" 
  -X POST 
  -d @newVersions.json 
  -H "Content-Type: application/json"
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

Related CLI command: [createManyVersions](udclient_createmanyversions.md).

**Parent topic:** [version resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_version.md)

