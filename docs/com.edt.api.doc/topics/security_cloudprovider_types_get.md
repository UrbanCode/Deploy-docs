# Get a list of cloud provider types

## Request

```
GET http://{hostname}:{port}
  /landscaper/security/cloudprovider/types
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/security/cloudprovider/types
```

## Example response

```
[
    {
        "id": "OPENSTACK",
        "name": "Openstack",
        "properties": [
            {
                "description": "The full URL to the Identity server. It should begin with 'http://' or 'https://'.",
                "id": "ff247cc6-f498-4dfb-8681-40528e2f2746",
                "label": "Identity URL",
                "name": "url",
                "required": true,
                "type": "VALIDATION_TEXT",
                "value": "http://localhost:5000/v2.0/"
            },
            {
                "description": "The timeout for provisioning a stack from the heat request.",
                "id": "fb5401ca-cd22-4b63-8663-017d5d9a8e22",
                "label": "Timeout in Mins",
                "name": "timeoutMins",
                "required": true,
                "type": "VALIDATION_TEXT",
                "value": "10"
            },
            {
                "description": "Use the default orchestration engine configured with the keystone.",
                "id": "2e900ebf-34e5-4c1a-bedd-20bf857f6fa1",
                "label": "Use default orchestration engine",
                "name": "useDefaultOrchestration",
                "required": false,
                "type": "CHECKBOX",
                "value": "true"
            },
            {
                "description": "Url of orchestration engine.",
                "id": "a674540a-ec07-4bcc-b1b1-da4c6bc980d7",
                "label": "Orchestration Engine URL",
                "name": "orchestrationEngineUrl",
                "required": true,
                "type": "VALIDATION_TEXT",
                "value": "http://localhost:8004"
            }
        ]
    },
    {
        "id": "AMAZON",
        "name": "Amazon EC2",
        "properties": [
            {
                "description": "The full URL to the Identity server. It should begin with 'http://' or 'https://'.",
                "id": "221f7473-aafa-4e2e-9667-cdc2dade2a5e",
                "label": "Identity URL",
                "name": "url",
                "required": true,
                "type": "VALIDATION_TEXT",
                "value": "http://localhost:5000/v2.0/"
            },
            {
                "description": "The timeout for provisioning a stack from the heat request.",
                "id": "2e934daa-9bdd-4917-9b9a-3b3dc399fc13",
                "label": "Timeout in Mins",
                "name": "timeoutMins",
                "required": true,
                "type": "VALIDATION_TEXT",
                "value": "10"
            },
            {
                "description": "Use the default orchestration engine configured with the keystone.",
                "id": "c3308df8-01d6-4708-bdb9-87720565ee15",
                "label": "Use default orchestration engine",
                "name": "useDefaultOrchestration",
                "required": false,
                "type": "CHECKBOX",
                "value": "true"
            },
            {
                "description": "Url of orchestration engine.",
                "id": "c7e83636-c290-42b0-8c4f-4966b92cd467",
                "label": "Orchestration Engine URL",
                "name": "orchestrationEngineUrl",
                "required": true,
                "type": "VALIDATION_TEXT",
                "value": "http://localhost:8004"
            }
        ]
    },
    {
        "id": "VMWARE",
        "name": "VMware",
        "properties": [
            {
                "description": "The full URL to the Identity server. It should begin with 'http://' or 'https://'.",
                "id": "2ba6b7ed-7d6b-4ae3-aea8-06319c0681a1",
                "label": "Identity URL",
                "name": "url",
                "required": true,
                "type": "VALIDATION_TEXT",
                "value": "http://localhost:5000/v2.0/"
            },
            {
                "description": "The timeout for provisioning a stack from the heat request.",
                "id": "a97a0feb-2179-496d-a2cd-31f9945de9db",
                "label": "Timeout in Mins",
                "name": "timeoutMins",
                "required": true,
                "type": "VALIDATION_TEXT",
                "value": "10"
            },
            {
                "description": "Use the default orchestration engine configured with the keystone.",
                "id": "1679e93f-ce60-406c-94eb-6d330d2f9a2a",
                "label": "Use default orchestration engine",
                "name": "useDefaultOrchestration",
                "required": false,
                "type": "CHECKBOX",
                "value": "true"
            },
            {
                "description": "Url of orchestration engine.",
                "id": "906db3b0-a390-4b33-b23e-806db257042c",
                "label": "Orchestration Engine URL",
                "name": "orchestrationEngineUrl",
                "required": true,
                "type": "VALIDATION_TEXT",
                "value": "http://localhost:8004"
            }
        ]
    }
]
```

**Parent topic:** [security/cloudprovider resource](../../com.edt.api.doc/topics/security_cloudprovider_.md)

