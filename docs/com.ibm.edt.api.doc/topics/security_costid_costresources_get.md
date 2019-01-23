# Get cost resource information from a cost center

## Request

```
GET http://{hostname}:{port}
  /landscaper/security/costcenter/{costCenterId}/costresources
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|costCenterId|string|true|ID of the cost center|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
   
  -H 'Accept: application/json'
  http://myserver.example.com:8080/landscaper/security/
  costcenter/0bce5aec-e4f4-4e51-a52c-dfe0a52aca96/costresources
```

## Example response

```
[
  {
    "id": "dd03b775-46be-4f59-8377-3c95fe94f5bd",
    "name": "Flavor1",
    "costCenterId": "0bce5aec-e4f4-4e51-a52c-dfe0a52aca96",
    "resourceType": "FLAVOR",
    "resourceId": "flavor1",
    "properties": [
      {
        "id": "b36cc354-f329-4907-aaf1-dfdb911e353d",
        "name": "cpu",
        "value": "2",
        "label": "",
        "secure": false
      },
      {
        "id": "520c1082-4865-4547-ae0a-d890339d1e0d",
        "name": "diskCount",
        "value": "1",
        "label": "",
        "secure": false
      },
      {
        "id": "8ce9a423-b87e-4324-9ffc-dc500287a983",
        "name": "diskSize",
        "value": "10",
        "label": "",
        "secure": false
      },
      {
        "id": "55b9118e-998a-489a-b8aa-7e461837c729",
        "name": "ramSize",
        "value": "4",
        "label": "",
        "secure": false
      }
    ]
  },
  {
    "id": "cc1132ee-1f8b-4d39-87e5-84c39c32fe12",
    "name": "default",
    "costCenterId": "0bce5aec-e4f4-4e51-a52c-dfe0a52aca96",
    "resourceType": "INSTANCE_TYPE",
    "resourceId": "default",
    "properties": [
      {
        "id": "f0a0cd19-65eb-494a-a410-38c1b7f797c1",
        "name": "default",
        "value": "true",
        "label": "",
        "secure": false
      },
      {
        "id": "80c79c41-5d45-462b-ab96-356dd7b2e34d",
        "name": "tag",
        "value": "default",
        "label": "",
        "secure": false
      }
    ]
  },
  {
    "id": "208b12e9-bf4f-4d47-bb0d-5859919600b4",
    "name": "Region A",
    "costCenterId": "0bce5aec-e4f4-4e51-a52c-dfe0a52aca96",
    "resourceType": "REGION",
    "resourceId": "a",
    "properties": [
      {
        "id": "44a66b9f-f8f9-4ad3-aca7-7d37c1b4172a",
        "name": "country",
        "value": "USA",
        "label": "",
        "secure": false
      },
      {
        "id": "f89daf3d-baf6-4ebf-9d4c-b6539046bbf4",
        "name": "default",
        "value": "true",
        "label": "",
        "secure": false
      }
    ]
  },
  {
    "id": "7c804609-3eb1-4e47-a6dd-0a8fc3237011",
    "name": "Region B",
    "costCenterId": "0bce5aec-e4f4-4e51-a52c-dfe0a52aca96",
    "resourceType": "REGION",
    "resourceId": "b",
    "properties": [
      {
        "id": "f5fbbd24-fbab-475b-88ea-14a14aaa40a2",
        "name": "country",
        "value": "USA",
        "label": "",
        "secure": false
      },
      {
        "id": "f9e2e52d-e220-4aca-9cff-d218d04399d1",
        "name": "default",
        "value": "false",
        "label": "",
        "secure": false
      }
    ]
  },
  {
    "id": "abfd37b2-a53f-412d-a6d6-799a6aa62d83",
    "name": "Volume 1",
    "costCenterId": "0bce5aec-e4f4-4e51-a52c-dfe0a52aca96",
    "resourceType": "VOLUME",
    "resourceId": "v1",
    "properties": [
      {
        "id": "acf508c3-5056-49f8-a6bb-0d8b7b7362b3",
        "name": "default",
        "value": "true",
        "label": "",
        "secure": false
      }
    ]
  }
]
```

**Parent topic:** [security/costcenter resource](../../com.ibm.edt.api.doc/topics/security_costcenter_.md)

