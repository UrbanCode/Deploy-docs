# List the components in an environment

This command lists the IBM UrbanCode Deploy components that are deployed to an environment.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/environment/{environmentId}/components
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|environmentId|string|true|ID of the environment|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/environment/32019dda-4da5-40b1-804b-307a9a2eeb44/components
```

## Example response

```
[
    {
        "name": "JPetStore-APP",
        "process": "Deploy application component",
        "version": "1"
    },
    {
        "name": "JPetStore-WEB",
        "process": "Deploy web component",
        "version": "1"
    },
    {
        "name": "JPetStore-DB",
        "process": "Deploy database component",
        "version": "1"
    }
]
```

**Parent topic:** [rest/environment resource](../../com.edt.api.doc/topics/rest_environment_.md)

