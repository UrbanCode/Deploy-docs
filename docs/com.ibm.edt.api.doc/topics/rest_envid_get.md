# Show information about an environment

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/environment/{environmentId}
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
  http://myserver.example.com:8080/landscaper/rest/environment/32019dda-4da5-40b1-804b-307a9a2eeb44
```

## Example response

```
{
    "id":"32019dda-4da5-40b1-804b-307a9a2eeb44",
    "name":"MyEnvironment",
    "blueprintName": "MyBlueprint",
    "blueprintUrl": "http:\/\/localhost:8080\/landscaper\/view\/projects?open=ucdpadmin_00000000_0000_0000_0000_000000000002-OrionContent\/Internal-Team\/MyBlueprint.yml",
    "stack_status":"CREATE_COMPLETE",
    "stack_status_reason":"Stack CREATE completed successfully",
    "creation_time": "2017-03-15T21:18:05Z",
    "owner":"admin",
    "created_by":"MyUserID",
    "regionName":"RegionOne",
    "cloudProjectName":"MyCloudProject",
    "parameters":
        {
             "OS::project_id":"b6a43fbeec6b4fd5afb56f977383a46d",
             "IBM::VMWare::User":"Administrator@cloud",
             "ucd_server_url":"http:\/\/myUCDserver.com:9080",
             "availability_zone":"TODO",
             "IBM::Cloud::Type":"VMWARE",
             "flavor":"m1.small",
             "IBM::VMWare::Host":"myVMWare.raleigh.ibm.com",
             "ucd_user":"admin",
             "IBM::VMWare::Port":"443",
             "OS::region":"RegionOne",
             "ucd_relay_url":"None",
             "IBM::NSX::User":"",
             "IBM::VMWare::Password":"******",
             "OS::stack_name":"MyEnvironment",
             "key_name":"TODO",
             "ucd_password":"******",
             "vmware_destination_folder":"",
             "network-id__for__VIS275":"VIS275",
             "IBM::Cloud":"035a544-7851-42ca-42c6-bca7-1d89e06e4c65",
             "IBM::NSX::Host":"",
             "OS::stack_id":"32019dda-4da5-40b1-bd49-95d171696cd6",
             "vmware_resource_pool":"resourcePool",
             "IBM::NSX::Password":"******",
             "IBM::UCD::USER":"MyID"},
        },
    "outputs": [
        {
            "output_value":"http:\/\/localhost:8080\/landscaper\/view\/projects?open=ucdpadmin_00000000_0000_0000_0000_000000000002-OrionContent\/Internal-Team\/MyBlueprint.yml",
            "description": "Blueprint Origin URL",
            "output_key": "blueprint_url"
        }
    ],
}
```

**Parent topic:** [rest/environment resource](../../com.ibm.edt.api.doc/topics/rest_environment_.md)

