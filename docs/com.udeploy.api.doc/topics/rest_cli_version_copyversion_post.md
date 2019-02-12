# Copy a component version with all of its properties

Do not use the keywords latest, latestVersion, or newest as the version name.

## Request

```
POST https://{hostname}:{port}
    /cli/version/copyVersion?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name or ID of the component|
|name|string|true|Name of the new version|
|from|string|true|Name of the version to copy|
|description|string|false|Description of the new version|
|type|string|false|Type to use for the new version \(incremental or full\); the default is the default version type for the component|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/
  version/copyVersion?component=MyComponent&name=NewCopiedVersion&
  from=ExistingVersion&type=full"
  -X POST
```

## Example response

```
{
  "properties": [],
  "propSheets": [{
    "properties": [],
    "id": "62ee0d83-97aa-4006-b4a7-933a803abdc3",
    "path": "components\/5ad2f8a2-88d3-4f55-94e0-499bdbc5f0a9\/versions\/2d9e369b-8ac9-45c0-a192-017c201820e6\/
    propSheetGroup\/propSheets\/62ee0d83-97aa-4006-b4a7-933a803abdc3",
    "version": 1,
    "versionCount": 1,
    "commit": 0,
    "versioned": true,
    "propSheetDef": {
      "id": "bce76bb6-b660-4f62-b23a-859cd3ac61c2",
      "path": "components\/5ad2f8a2-88d3-4f55-94e0-499bdbc5f0a9\/versionPropSheetDef",
      "version": 1,
      "versionCount": 1,
      "commit": 9,
      "resolveHttpValuesUrl": "property\/propSheetDef\/
      components%265ad2f8a2-88d3-4f55-94e0-499bdbc5f0a9%26versionPropSheetDef.-1\/resolveHttpValues",
      "versioned": true
    }
  }],
  "totalSize": 0,
  "totalCount": 0,
  "id": "2d9e369b-8ac9-45c0-a192-017c201820e6",
  "name": "NewCopiedVersion",
  "type": "FULL",
  "created": 1443806239480,
  "active": true,
  "archived": false,
  "sizeOnDisk": 0
}

```

Related CLI command: [copyVersion](udclient_copyversion.md).

**Parent topic:** [version resource](../../com.udeploy.api.doc/topics/rest_cli_version.md)

