# List the new networks in an environment

This command lists the networks in the environment that were created when the environment was provisioned.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/environment/{environmentId}/networks
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
  http://myserver.example.com:8080/landscaper/rest/environment/32019dda-4da5-40b1-804b-307a9a2eeb44/networks
```

## Example response

```
[
  {
    "subnets": [],
    "name": "my-network",
    "region": "us-east-1",
    "state": "available",
    "cidr": "152.93.0.0/16",
    "id": "vpc-f5638f95"
    }
]
```

**Parent topic:** [rest/environment resource](../../com.edt.api.doc/topics/rest_environment_.md)

