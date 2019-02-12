# Get the console output of a node

This command returns console output of a given instance \(node\) in an environment.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/environment/{environmentId}/instance/{instanceId}/consoleOutput
Accept: text/plain

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|instanceId|string|true|ID of the instance \(node\)|
|environmentId|string|true|ID of the environment|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`text/plain`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/
  environment/224b329b-08bf-4176-8317-f1f3135c2037/
  instance/5f9474a4-5596-4bde-a7f4-3afda83ece52/consoleOutput" 
  -H "Accept: text/plain"
```

## Example response

```
Cloud-init v. 0.7.5 finished at Tue, 05 Jan 2016 20:32:02 +0000. 
Datasource DataSourceConfigDriveNet [net,ver=2][source=/dev/sr0].  
Up 42.26 seconds
Starting sendmail: [  OK  ]
Starting sm-client: [  OK  ]
Starting ovirt-guest-agent: [FAILED]
Starting tuned: [  OK  ]
Starting crond: [  OK  ]
Starting rhsmcertd...[  OK  ]

Red Hat Enterprise Linux Server release 6.7 (Santiago)
Kernel 2.6.32-573.7.1.el6.x86_64 on an x86_64

mynewsystem login:

```

**Parent topic:** [rest/environment resource](../../com.edt.api.doc/topics/rest_environment_.md)

