# Show information about resource types

Use the URL query parameter "t=resourceType" to specify the resource type. To specify multiple resource types, separate additional query parameters with an ampersand \(&\).

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/cloud/resourcesAttributes
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/cloud/resourcesAttributes?
  t=OS::Nova::Server
```

## Example response

```
{
    "OS::Nova::Server": {
        "accessIPv4": {
            "description": "The manually assigned alternative public 
            IPv4 address of the server."
        },
        "accessIPv6": {
            "description": "The manually assigned alternative public IPv6 
            address of the server."
        },
        "addresses": {
            "description": "A dict of all network addresses with 
            correspondingport_id."
        },
        "first_address": {
            "description": "Convenience attribute to fetch the first assigned 
            network address, or an empty string if nothing has been assigned 
            at this time. Result may not be predictable if the server has 
            addresses from more than one network."
        },
        "instance_name": {
            "description": "AWS compatible instance name."
        },
        "networks": {
            "description": "A dict of assigned network addresses of the form: 
            {\"public\": [ip1, ip2...], \"private\": [ip3, ip4]}."
        },
        "show": {
            "description": "A dict of all server details as returned by 
            the API."
        }
    }
}
```

**Parent topic:** [rest/cloud resource](../../com.edt.api.doc/topics/rest_cloud.md)

