# Get information about an agent

This command returns a JSON representation of an agent.

## Request

```
GET https://{hostname}:{port}
    /cli/agentCLI/info?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|agent|string|true|Name or ID of the agent|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/agentCLI/info
  ?agent=myAgent"
```

## Example response

```
{
  "id": "18cc6e9c-0c18-44bc-b34d-53c8609d9c44",
  "securityResourceId": "4c9f52c0-6f90-4e6a-94a9-5a68c8081796",
  "name": "myAgent",
  "active": true,
  "licensed": false,
  "licenseType": "NONE",
  "status": "ONLINE",
  "version": "6.2.5.0.918945",
  "lastContact": 1498229460223,
  "dateCreated": 1497277343513,
  "workingDirectory": "\/opt\/ibm-ucd\/agent\/var\/work\/",
  "impersonationPassword": "****",
  "impersonationUseSudo": false,
  "impersonationForce": false,
  "tags": [],
  "security": {
    "read": true,
    "execute": true,
    "Add to Agent Pool": true,
    "Create Resources": true,
    "Delete": true,
    "Edit Basic Settings": true,
    "Execute on Agents": true,
    "Manage Impersonation": true,
    "Manage Properties": true,
    "Manage Teams": true,
    "Manage Version Imports": true,
    "View Agents": true
  },
  "propSheet": {
    "id": "42763bdd-66b5-4021-9a57-62ba3dd745fd",
    "path": "agents\/18cc6e9c-0c18-44bc-b34d-53c8609d9c44\/propSheet",
    "version": 2,
    "versionCount": 2,
    "commit": 55,
    "versioned": true
  },
  "extendedSecurity": {
    "read": true,
    "execute": true,
    "Add to Agent Pool": true,
    "Create Resources": true,
    "Delete": true,
    "Edit Basic Settings": true,
    "Execute on Agents": true,
    "Manage Impersonation": true,
    "Manage Properties": true,
    "Manage Teams": true,
    "Manage Version Imports": true,
    "View Agents": true,
    "teams": [{
      "teamId": "8213c4ec-1f66-4b4a-9a73-e24bf8b8102f",
      "teamLabel": "My team",
      "resourceTypeId": "20000000000000000000000000000106",
      "resourceTypeName": "Agent"
    }]
  }
}

```

Related CLI command: [getAgent](udclient_getagent.md).

**Parent topic:** [agentCLI resource](../../com.udeploy.api.doc/topics/rest_cli_agentcli.md)

