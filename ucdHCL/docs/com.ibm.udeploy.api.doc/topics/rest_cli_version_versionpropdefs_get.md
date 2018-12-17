# List the version property definitions for a component

These properties are available to each version of the component.

## Request

```
GET https://{hostname}:{port}
    /cli/version/versionPropDefs?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name or ID of the component|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example response

```
[
  {
    "id": "870bc2f5-55e2-4cb9-b3ab-f750688754b9",
    "name": "Prop1",
    "label": "Prop1",
    "pattern": "",
    "type": "CHECKBOX",
    "value": "true",
    "required": false,
    "description": ""
  },
  {
    "id": "ee02cbf0-9fc9-465e-a37f-754c40222d0d",
    "name": "Prop2",
    "label": "",
    "pattern": "",
    "type": "TEXT",
    "value": "prop2",
    "required": false,
    "description": ""
  }
]
```

Related CLI command: [getComponentVersionPropDefs](udclient_getcomponentversionpropdefs.md).

**Parent topic:** [version resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_version.md)

