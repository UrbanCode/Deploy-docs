# Create a snapshot

This command creates a snapshot by specifying the components \(optional\) for the snapshot, rather than taking a snapshot of an environment.

## Request

```
PUT https://{hostname}:{port}
    /cli/snapshot/createSnapshot
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "application": "Application name or ID",
  "description": "Description",
  "name": "Snapshot name",
  "versions": "JSON array of mappings from components to 
  versions, such as [{\"JPetStore-APP\": \"latest\"}, {\"
  JPetStore-DB\": \"1.0\"}]"
}

```

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/snapshot/createSnapshot"
  -X PUT -d @newSnapshot.json
```

## Example JSON request

```
{
  "name": "My snapshot",
  "application": "JPetStore",
  "description": "JPetStore snapshot",
  "versions": [
    {"JPetStore-APP": "1.1"}, 
    {"JPetStore-DB": "1.0"}, 
    {"JPetStore-WEB": "1.1"}
  ]
}
```

## Example JSON request

You can also use the keywords `latest`, `latestVersion`, and `newest` in place of component version names. In this case, the process uses the most recently created component version. The following example shows how you can use these keywords in the JSON request.

```
{
  "name": "My snapshot",
  "application": "JPetStore",
  "description": "Snapshots of most recently created component versions",
  "versions": [
    {"JPetStore-APP": "latest"}, 
    {"JPetStore-DB": "latestVersion"}, 
    {"JPetStore-WEB": "newest"}
  ]
}
```

## Example response

```
{
  "id": "ff9274d4-bc3d-493c-90aa-5020e2fda56d",
  "name": "My snapshot",
  "description": "JPetStore snapshot",
  "created": 1391451659050,
  "active": true,
  "locked": false
}
```

Related CLI command: [createSnapshot](udclient_createsnapshot.md).

**Parent topic:** [snapshot resource](../../com.udeploy.api.doc/topics/rest_cli_snapshot.md)

