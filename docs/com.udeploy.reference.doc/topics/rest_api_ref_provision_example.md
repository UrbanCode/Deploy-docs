# Provisioning environments by using REST commands: An example

The following example describes how to use the REST commands to provision an environment through the blueprint design server and engine.

Create a blueprint and ensure that you can provision an environment from the blueprint by using the blueprint designer user interface.

To provision environments with REST commands, you must have the following information:

-   **The ID of the cloud project to use**

    You can get this information from this REST command: [List cloud projects](../../com.edt.api.doc/topics/security_cloudproject__get.md).

-   **The name of the blueprint and the location of the blueprint on the blueprint design server**

    You can get this information from this REST command: [List blueprints](../../com.edt.api.doc/topics/rest_blueprint__get.md).

-   **The name and location of the configuration file on the blueprint design server \(Optional\)**

    To use a configuration file, you must have the name and complete location of that file. You can get this information from this REST command: [List configuration files for a blueprint](../../com.edt.api.doc/topics/rest_bpid_configuration_get.md).

-   **The parameters that are required to provision an environment from the blueprint**

    To provision an environment from a blueprint, you must specify the parameters for that blueprint. You can see the required parameters for a blueprint by clicking **Provision** and selecting the blueprint. You can also get this information from these REST commands: [List the parameters required to provision a blueprint](../../com.edt.api.doc/topics/rest_bpid_parameters_get.md) or [List the parameters required to provision a blueprint with a configuration file](../../com.edt.api.doc/topics/rest_bpid_confid_parameters_get.md).

    **Note:** For the command to be successful, you must provide exactly these parameters. Any missing parameters or additional parameters cause the command to fail.

-   **A session key for the blueprint design server**

    The session key authenticates you to the server. You can get a session key by running a command on the server with a user name and password and examining the session key in the return headers. See [Authenticating for REST commands](rest_api_ref_authenticating.md).


To provision an environment from the API, use this REST PUT command: [Provision a blueprint](../../com.edt.api.doc/topics/rest_bpid_deploy_put.md).

Use the following URL string for the request:

```
http://hostname:port/landscaper/rest/blueprint/\{blueprintId\}/deploy
```

Use the host name and port of the blueprint designer for `hostname` and `port` and the name of the blueprint for `\{blueprintId\}`.

Include the following headers with the PUT request:

|Header|Example|Description|
|------|-------|-----------|
|UCR\_SESSION\_KEY|`347e9240-dcc9-424e-af31-3614df52b245`|The session key that you retrieve from running a simple command with a user name and password|
|Accept|`application/json`|Specify `application/json` as the type of information that the command returns|
|Content-Type|`application/json`|Specify `application/json` as the type of information that you are sending to the command|
|Location|`/landscaper/orion/file/jsmith_00000000_0000_0000_0000_000000000002- OrionContent/Internal-Team/myBlueprint/myBlueprint.yml`|The location of the blueprint on the blueprint design server|
|X-Region-Name|`MyCloudRegion`|\(Optional\) The region for the environment|

Pass a JSON document that is similar to the following example as the request body. This example uses an authentication token for the server instead of a user name and password.

```
{
  "environmentName": "myNewEnvironment1",
  "configuration": "myConfigFile",
  "cloudProjectId":"3d16879f-7b43-4909-9862-12767dad7f04",
  "configurationLocation":"/landscaper/orion/file/jsmith_00000000_2-OrionContent/default/configurations/myConfigFile.yml",
  "parameters": {
    "availability_zone" : "nova",
    "flavor" : "m1.tiny",
    "key_name" : "myKey",
    "ucd_password":"cc99a431-d96c-4154-99d6-1a5532275015",
    "ucd_relay_url":"None",
    "ucd_server_url":"http://ucd.example.com:9080",
    "ucd_user":"PasswordIsAuthToken"
  },
  "teamMappings":[],
  "validate": "true"
}
```

This JSON document contains the following information:

|JSON property|Example|Description|
|-------------|-------|-----------|
|cloudProjectId|`3d16879f-7b43-4909-9862-12767dad7f04`|The ID of the cloud project; to get this ID, you can use the command [List cloud projects](../../com.edt.api.doc/topics/security_cloudproject__get.md)| |
|configuration|`myConfigFile`|\(Optional\) The name of the configuration file to use| |
|configurationLocation|`/landscaper/orion/file/jsmith_00000000_2-OrionContent/default/configurations/myConfigFile.yml`|The location of the configuration file on the server| |
|environmentName|myNewEnvironment1|A name for the new environment| |
|parameters|`{ "availability_zone" : "nova", "flavor" : "m1.tiny", "key_name" : "myKey", "ucd_password":"cc99a431-d96c-4154-99d6-1a5532275015", "ucd_relay_url":"None", "ucd_server_url":"http://ucd.example.com:9080", "ucd_user":"PasswordIsAuthToken" }`|A JSON array of parameters to pass to the provisioning process, including the parameters that you would specify if you provisioned the environment from the designer server user interface. To get a list of the required parameters, use the command [List the parameters required to provision a blueprint](../../com.edt.api.doc/topics/rest_bpid_parameters_get.md) or [List the parameters required to provision a blueprint with a configuration file](../../com.edt.api.doc/topics/rest_bpid_confid_parameters_get.md).|
|teamMappings| |An array of teams to add the environment to|
|validate|`true`|Whether to validate the request before running it|

If you use the Linux™ program curl, the command might look like the following example. This command must be written on a single line.

```
curl -k -u jsmith:passwd
  "http://myserver.example.com:8080/landscaper/rest/blueprint/myBlueprint/deploy" 
  -X PUT 
  -H "Accept: application/json" 
  -H "Content-Type: application/json" 
  -H "UCR_SESSION_KEY: 347e9240-dcc9-424e-af31-3614df52b245" 
  -H "Location:
  /landscaper/orion/file/jsmith_00000000_0000_0000_0000_000000000002- OrionContent/Internal-Team/myBlueprint/myBlueprint.yml" 
  -H "X-Region-Name: MyCloudRegion" 
  -d @provisionEnvironment.json
```

This example command uses a JSON file that is named newEnvironment.json.

**Parent topic:** [REST API reference](../../com.udeploy.reference.doc/topics/rest_api_ref_overview.md)

