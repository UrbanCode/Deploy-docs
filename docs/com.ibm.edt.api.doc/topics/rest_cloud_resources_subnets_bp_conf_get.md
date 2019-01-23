# List the subnets for a cloud type

This command lists the subnets on the appropriate cloud for a specified configuration file.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/cloud/resources/subnets/blueprint/{blueprint}/configuration/{configuration}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|blueprint|string|true|The blueprint ID|
|configuration|string|true|The configuration file ID|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/cloud/resources/
  subnets/blueprint/MyBlueprint/
  configuration/MyConfigOpenStack
```

## Example response

```
[
    {
        "allocation_pools": [
            {
                "end": "10.5.5.254",
                "start": "10.5.5.2"
            }
        ],
        "cidr": "10.5.5.0/24",
        "dns_nameservers": [],
        "enable_dhcp": true,
        "gateway_ip": "10.5.5.1",
        "host_routes": [],
        "id": "1b148d05-f72d-48d5-8337-57217617d6f8",
        "ip_version": 4,
        "name": "demo-net >> demo-subnet",
        "network_id": "6b17edbc-b664-4bc6-9c60-c5ea9a54c019",
        "tenant_id": "3f1b2342cefd4dsdgdfg4ceec67348a4c"
    },
    {
        "allocation_pools": [
            {
                "end": "10.10.158.100",
                "start": "10.10.158.10"
            }
        ],
        "cidr": "10.10.0.0/16",
        "dns_nameservers": [],
        "enable_dhcp": false,
        "gateway_ip": "10.10.0.1",
        "host_routes": [],
        "id": "c0c8a423-cc93-40fc-8076-7acfd561bc29",
        "ip_version": 4,
        "name": "ext-net >> ext-subnet",
        "network_id": "fbd65c61-c78b-4fb9-a123-97c08a5d4e2e",
        "tenant_id": "3f1b8025ce23420f80b4ceec67348a4c"
    }
]
```

**Parent topic:** [rest/cloud resource](../../com.ibm.edt.api.doc/topics/rest_cloud.md)

