# Get all children or descendants of a resource template

Results include the base resource and resources inherited from ancestors of this template.

## Request

```
GET https://{hostname}:{port}
    /cli/resourceTemplate/getChildren?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|template|string|true|Name or ID of the resource template. If this is a blueprint identified by name rather than ID, a parent application must also be specified using the -application flag.|
|application|string|false|Name or ID of the parent application. Required if the template represents an application blueprint identified by name.|
|recursive|boolean|false|Get all descendants of the template \(not just immediate children\). Default is false.|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/
  resourceTemplate/getChildren?template=MyResourceTemplate" 

```

Related CLI command: [getResourceTemplateChildren](udclient_getresourcetemplatechildren.md).

**Parent topic:** [resourceTemplate resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_resourcetemplate.md)

