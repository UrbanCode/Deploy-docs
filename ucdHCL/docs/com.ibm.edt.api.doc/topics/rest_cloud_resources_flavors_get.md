# List the flavors of images

This command returns a list of the image flavors on the cloud with which the current user is associated.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/cloud/resources/flavors
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/cloud/resources/flavors
```

## Example response

```
[
    {
        "OS-FLV-DISABLED:disabled": false,
        "OS-FLV-EXT-DATA:ephemeral": 0,
        "disk": "80",
        "id": "m1.large",
        "links": [
            {
                "href": "http://cloud.example.com:8774/v2/abc/flavors/4",
                "rel": "self",
                "type": null
            },
            {
                "href": "http://cloud.example.com:8774/v2/abc/flavors/4",
                "rel": "bookmark",
                "type": null
            }
        ],
        "name": "m1.large",
        "os-flavor-access:is_public": true,
        "public": true,
        "ram": 8192,
        "rxtx_cap": null,
        "rxtx_factor": 1,
        "rxtx_quota": null,
        "swap": "",
        "vcpus": "4"
    },
    {
        "OS-FLV-DISABLED:disabled": false,
        "OS-FLV-EXT-DATA:ephemeral": 0,
        "disk": "40",
        "id": "m1.medium",
        "links": [
            {
                "href": "http://cloud.example.com:8774/v2/abc/flavors/3",
                "rel": "self",
                "type": null
            },
            {
                "href": "http://cloud.example.com:8774/v2/abc/flavors/3",
                "rel": "bookmark",
                "type": null
            }
        ],
        "name": "m1.medium",
        "os-flavor-access:is_public": true,
        "public": true,
        "ram": 4096,
        "rxtx_cap": null,
        "rxtx_factor": 1,
        "rxtx_quota": null,
        "swap": "",
        "vcpus": "2"
    }
]
```

**Parent topic:** [rest/cloud resource](../../com.ibm.edt.api.doc/topics/rest_cloud.md)

