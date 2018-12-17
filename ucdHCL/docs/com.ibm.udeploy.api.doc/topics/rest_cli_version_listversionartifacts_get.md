# Get the list of artifacts for a version

## Request

```
GET https://{hostname}:{port}
    /cli/version/listVersionArtifacts?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|false|Name or ID of the component; this value is required if you specify the version name instead of ID|
|version|string|true|Name or ID of the version|
|singleFilePath|string|false|Optional path to an individual version artifact to list.|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Examples

**Note:** By default, this command lists only the files and folders in the root folder, as in the following example. The command does not recurse into other folders.

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/version/listVersionArtifacts
  ?component=MyComponent&version=1.0"
```

The result of this command looks like the following example code:

```
[
  {
    "name": "fileA.txt",
    "path": "fileA.txt",
    "version": 1,
    "$ref": "fileA.txt/",
    "type": "file",
    "children": false,
    "lastModified": 1449262065000,
    "length": 0,
    "metaOnly": false
  },
  {
    "name": "folderA",
    "path": "folderA",
    "version": 1,
    "$ref": "folderA/",
    "type": "folder",
    "children": true,
    "lastModified": 1449262065000,
    "length": 0,
    "metaOnly": false
  },
  {
    "name": "folderB",
    "path": "folderB",
    "version": 1,
    "$ref": "folderB/",
    "type": "folder",
    "children": true,
    "lastModified": 1449262065000,
    "length": 0,
    "metaOnly": false
  }
]
```

**Note:** To list files and folders that are not in the root folder, you must specify the singleFilePath parameter, as in the following example:

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/version/listVersionArtifacts
  ?component=MyComponent&version=1.0&singleFilePath=folderA"
```

The result of this command includes only the contents of the specified folder, as in the following example:

```
[
  {
    "name": "fileA.txt",
    "path": "folderA/fileA.txt",
    "version": 1,
    "$ref": "folderA/fileA.txt/",
    "type": "file",
    "children": false,
    "lastModified": 1451488971000,
    "length": 0,
    "metaOnly": false
  }
]
```

Related CLI command: [listArtifacts](udclient_listartifacts.md).

**Parent topic:** [version resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_version.md)

