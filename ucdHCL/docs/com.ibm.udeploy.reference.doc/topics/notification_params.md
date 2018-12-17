# Parameters for notification templates

Depending on the context of the notification, you can insert parameters into the notification template. When the notification is sent, these parameters are replaced with values such as the names and information about applications, components, and processes.

**Note:** Not all parameters are available in all contexts. For example, when you run a generic process, parameters that are related to applications are not available.

|Parameter|Description|Example|
|---------|-----------|-------|
|$externalUrl\(\)|The URL of the server|`http://myserver.example.com:8443`|
|$request|The request that caused the notification, such as an application process request|`ApplicationProcessRequest#74ae3853-3444-4d7d-a0f3-68107f47b29f`|

|Parameter|Description|Example|
|---------|-----------|-------|
|$application.getName\(\)|The name of the application|`My application`|
|$application.getId\(\)|The ID of the application|`b37054b7-7b20-49b6-973d-fd0ee0b1b62b`|
|$application.getDescription\(\)|The description of the application|`This is my application`|
|$application.getPath\(\)|The URL path of the application|`applications/b37054b7-7b20-49b6-973d-fd0ee0b1b62b`|

|Parameter|Description|Example|
|---------|-----------|-------|
|$applicationProcess.getId\(\)|The ID of the application process|`50d5bca2-d8d9-47f2-a0ce-5b75b3f24d3b`|
|$applicationProcess.getName\(\)|The name of the application process|`Deploy application`|

|Parameter|Description|Example|
|---------|-----------|-------|
|$environment.getId\(\)|The ID of the application|`072a54df-8c3a-4b23-a660-323cf205c86c`|
|$environment.getName\(\)|The name of the environment|`Environment 1`|
|$environment.getDescription\(\)|The description of the environment| |
|$environment.getColor\(\)|The color that is assigned to the environment in the table of environments|`#00B2EF`|
|$environment.isRequireApprovals\(\)|True if the environment requires approvals| |

You can retrieve an array of application process versions with the parameter $versions. For the size of the array, use the parameter $versions.size\(\). To access individual versions within this array, access them with a loop as in the following example:

```
<div class="data-table-container">
#if ($versions.size() > 0)
  <h3>Versions Included:</h3>
  <table class="data-table" cellpadding="4" cellspacing="1" width="100%">
   <thead class="data-table-head">
      <th style="text-align:left;" scope="col" valign="middle">Component</th>
      <th style="text-align:left;" scope="col" valign="middle">Version</th>
      <th style="text-align:left;" scope="col" valign="middle">Description</th>
   </thead>
   <tbody>
    #foreach ($version in $versions)
      #if ($velocityCount % 2 == 1)
          #set ($rowClass = "odd")
      #else
          #set ($rowClass = "even")
      #end
      <tr class="$rowClass">
       <td>$version.getComponent().getName()</td>
       <td>$version.getName()</td>
       <td>
         #if ($version.getDescription())
           $version.getDescription()
         #end
       </td>
     </tr>
    #end
   </tbody>
  </table>
#else
  <h3>No Versions Included</h3>
#end
</div>
```

Within the loop, you can access information about the individual versions with the parameters in the following table:

|Parameter|Description|Example|
|---------|-----------|-------|
|$version.getName\(\)|The name of the component version| |
|$version.getComponent\(\)|The component| |

|Parameter|Description|Example|
|---------|-----------|-------|
|$snapshot.getId\(\)|The ID of the snapshot|`5d95883f-be45-4abe-8664-3ca6a7635a12`|
|$snapshot.getName\(\)|The name of the snapshot|`My snapshot`|
|$snapshot.getDescription\(\)|The description of the snapshot| |
|$snapshot.getCreatedDate\(\)|The creation date of the snapshot|`Fri Mar 20 09:56:42 EDT 2015`|
|$snapshot.getCreatedTime\(\)|The creation time of the snapshot in UNIX™ format|`1418136059500`|

|Parameter|Description|Example|
|---------|-----------|-------|
|$user.getId\(\)|The ID of the user|`20000000000000000000000001000000`|
|$user.getName\(\)|The user name|`jsmith`|
|$user.getActualName\(\)|The full name of the user|`Joe Smith`|
|$user.getEmail\(\)|The email address of the user|`jsmith@example.com`|

|Parameter|Description|Example|
|---------|-----------|-------|
|$processname|The name of the requested process| |
|$scheduledDate|The date for which the process is scheduled|`Fri Apr 10 13:16:53 EDT 2015`|
|$appRequest.getDescription\(\)|The description of the application process request| |
|$requestType|The type of request|`applicationProcessRequest`|
|$roles|The roles that a user must have to approve the request|`[Role: Administrator]`|
|$appRequest|For application process requests, the application process request ID|`ApplicationProcessRequest#81701a8b-332c-47dd-8efe-87aab8fa2dfd`|

