# List the security groups on the cloud

This command returns a list of the security groups on the cloud with which the current user is associated.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/cloud/resources/securitygroups
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/cloud/resources/
  securitygroups
```

## Example response

```
[
    {
        "category": "security",
        "description": "default",
        "icon": "images/editor/SecurityGroup_Palette.gif",
        "id": "0beb3f8b-gth4-4ee3-ac0d-742c236d206e",
        "links": null,
        "name": "default",
        "rules": [
            {
                "from_port": 1,
                "group": {
                    "name": null,
                    "tenant_id": null
                },
                "id": "9143409-1cc9-433f-97d4-1c891a1a1060",
                "ip_protocol": "udp",
                "ip_range": {
                    "cidr": "0.0.0.0/0"
                },
                "name": null,
                "parent_group_id": "0beb3f8b-gth4-4ee3-ac0d-742c236d206e",
                "to_port": 65535
            },
            {
                "from_port": 1,
                "group": {
                    "name": null,
                    "tenant_id": null
                },
                "id": "af4545e0-0faf-41be-aad1-b867b383771f",
                "ip_protocol": "tcp",
                "ip_range": {
                    "cidr": "0.0.0.0/0"
                },
                "name": null,
                "parent_group_id": "0beb3f8b-gth4-4ee3-ac0d-742c236d206e",
                "to_port": 65535
            },
            {
                "from_port": -1,
                "group": {
                    "name": null,
                    "tenant_id": null
                },
                "id": "d3af2345-bc3f-4921-a0e7-b0a8b574b210",
                "ip_protocol": "icmp",
                "ip_range": {
                    "cidr": "0.0.0.0/0"
                },
                "name": null,
                "parent_group_id": "0beb3f8b-gth4-4ee3-ac0d-742c236d206e",
                "to_port": -1
            }
        ],
        "tenant_id": "3f1b8025ce23420f80b4ceec67348a4c"
    }
]
```

**Parent topic:** [rest/cloud resource](../../com.ibm.edt.api.doc/topics/rest_cloud.md)

