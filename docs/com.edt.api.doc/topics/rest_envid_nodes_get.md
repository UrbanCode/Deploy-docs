# List the nodes in an environment

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/environment/{environmentId}/nodes
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
  http://myserver.example.com:8080/landscaper/rest/environment
  /32019dda-4da5-40b1-804b-307a9a2eeb44/nodes
```

## Example response

```
[
    {
        "OS-DCF:diskConfig": "MANUAL",
        "OS-EXT-AZ:availability_zone": "nova",
        "OS-EXT-SRV-ATTR:host": "node004.mgt",
        "OS-EXT-SRV-ATTR:hypervisor_hostname": "node004.mgt",
        "OS-EXT-SRV-ATTR:instance_name": "instance-000003f5",
        "OS-EXT-STS:power_state": "1",
        "OS-EXT-STS:task_state": null,
        "OS-EXT-STS:vm_state": "active",
        "OS-SRV-USG:launched_at": "2014-06-23T15:44:14.000000",
        "OS-SRV-USG:terminated_at": null,
        "accessIPv4": "",
        "accessIPv6": "",
        "addresses": {
            "addresses": {
                "demo-net": [
                    {
                        "OS-EXT-IPS-MAC:mac_addr": "12:23:3e:f3:b5:3b",
                        "OS-EXT-IPS:type": "fixed",
                        "addr": "10.5.5.82",
                        "version": "4"
                    }
                ]
            }
        },
        "adminPass": null,
        "config_drive": "",
        "created": "2014-06-23T15:44:08Z",
        "fault": null,
        "flavor": {
            "OS-FLV-DISABLED:disabled": null,
            "OS-FLV-EXT-DATA:ephemeral": null,
            "disk": null,
            "id": "2",
            "links": [
                {
                    "href": "http://cloud.example.com:8774/
                    3f1b8025cefd4d0f80b4ceec345628a4c/flavors/2",
                    "rel": "bookmark",
                    "type": null
                }
            ],
            "name": null,
            "os-flavor-access:is_public": null,
            "public": null,
            "ram": null,
            "rxtx_cap": null,
            "rxtx_factor": null,
            "rxtx_quota": null,
            "swap": null,
            "vcpus": null
        },
        "flavor_display_name": "m1.small",
        "hostId": "061908c5848e79fb48096f9915a12f9dba7c313e94e73728757b5f18",
        "id": "37976d75-83be-4ef1-bf3b-2f50d84d34562",
        "image": {
            "OS-EXT-IMG-SIZE:size": null,
            "created": null,
            "id": "53f6a6a9-0654-47c3-8ac4-cb82e250f75c",
            "links": [
                {
                    "href": "http://cloud.example.com:8774/
                    3f1b8025cefd4d0f80b4ceec345628a4c/images/
                    53f6a6a9-0654-47c3-8ac4-cb82e250f75c",
                    "rel": "bookmark",
                    "type": null
                }
            ],
            "metadata": null,
            "minDisk": null,
            "minRam": null,
            "name": null,
            "progress": null,
            "server": null,
            "status": null,
            "updated": null
        },
        "image_display_name": "Linux image 1",
        "key_name": "testkey",
        "links": [
            {
                "href": "http://cloud.example.com:8774/v2/
                3f1b8025cefd4d0f80b4ceec3f1b8025cefd4d0f80b4ceec345628a4c7348a4c/servers/
                37976d75-83be-4ef1-bf3b-2f50d84d34562",
                "rel": "self",
                "type": null
            },
            {
                "href": "http://cloud.example.com:8774/3f1b8025cefd4d0f80b4ceec345628a4c/
                servers/37976d75-83be-4ef1-bf3b-2f50d84d34562",
                "rel": "bookmark",
                "type": null
            }
        ],
        "metadata": {},
        "name": "Environment1",
        "os-extended-volumes:volumes_attached": [],
        "progress": 0,
        "security_groups": [
            {
                "description": null,
                "id": null,
                "links": null,
                "name": "default",
                "rules": null,
                "tenant_id": null
            }
        ],
        "status": "ACTIVE",
        "tenant_id": "3f1b8025cefd4d0f80b4453567348a4c",
        "updated": "2014-06-23T15:44:14Z",
        "user_id": "cec82d8fb55d4d98563ebdcaf8ba6a197",
        "uuid": null
    }
]
```

**Parent topic:** [rest/environment resource](../../com.edt.api.doc/topics/rest_environment_.md)

