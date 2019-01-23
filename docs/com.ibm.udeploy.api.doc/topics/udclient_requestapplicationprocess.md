# requestApplicationProcess

Run an application process

A version may be set to 'latest' to deploy the latest version of that component.

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  requestApplicationProcess [JSON file]
```

## Parameters

None.

## Template

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "application": "Application name or ID",
  "applicationProcess": "Application process name or ID",
  "date": "Date and time to schedule the process for. 
  (Optional) Supports unix timecodes or the format yyyy-mm-
  dd HH:mm",
  "description": "Description for the request (Optional)",
  "environment": "Environment name or ID",
  "onlyChanged": "Specify false to force deployment of 
  versions that are already in the inventory (Optional)",
  "post-deploy-message": "The body of the PUT message. You 
  can use the variable ${p:finalStatus}, which holds the 
  state of the process. The possible states are:Success, 
  Failure, Approval Rejected, Awaiting Approval, Running, 
  Scheduled, Cancelled, and Unknown. (Optional)",
  "post-deploy-put-url": "The URL that the post-deploy-
  message is PUT to. (Optional)",
  "properties": {"Property name": "Property value 
  (Optional)"},
  "recurrencePattern": "To make a scheduled process recur, 
  specify 'D' (daily), 'W' (weekly), or 'M' (monthly). 
  (Optional)",
  "snapshot": "Snapshot name or ID (Optional)",
  "versions": [{
    "component": "Component name or ID for the version, if 
  you are using version name instead of ID.",
    "version": "Version name or ID (Repeat as necessary. 
  Not used with snapshots)"
  }]
}

```

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  requestApplicationProcess runProcess.json
```

## Example JSON request

```
{
  "application": "JPetStore",
  "description": "Requesting deployment",
  "applicationProcess": "Deploy JPetStore",
  "environment": "Tutorial environment 1",
  "onlyChanged": "false",
  "properties": {
    "Prop1": "value1"
  },
  "versions": [
    {
      "version": "1.0",
      "component": "JPetStore-APP"
    },
    {
      "version": "1.0",
      "component": "JPetStore-WEB"
    },
    {
      "version": "1.0",
      "component": "JPetStore-DB"
    }
  ]
}
```

## Example JSON request

You can also use the keywords `latest`, `latestVersion`, and `newest` in place of component version names. In this case, the process uses the most recently created component version. The following example shows how you can use these keywords in the JSON request.

```
{
  "application": "JPetStore",
  "description": "Deploying newest versions",
  "applicationProcess": "Deploy JPetStore",
  "environment": "Tutorial environment 1",
  "onlyChanged": "false",
  "properties": {
    "Prop1": "value1"
  },
  "versions": [
    {
      "version": "newest",
      "component": "JPetStore-APP"
    },
    {
      "version": "latest",
      "component": "JPetStore-WEB"
    },
    {
      "version": "latestVersion",
      "component": "JPetStore-DB"
    }
  ]
}
```

## Example response

```
{
  "requestId": "f7e7b00d-8ea6-4a95-ad74-0ff853125232"
}
```

Related REST command: [Run an application process](rest_cli_applicationprocessrequest_request_put.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

