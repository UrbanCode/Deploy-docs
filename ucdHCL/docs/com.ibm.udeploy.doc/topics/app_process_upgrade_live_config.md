# Update from Live Configuration

This step is a wrapper step for updating a resource with the configuration information from an application server.

Applications, components, and generic processes share some process steps. This step applies to application processes, component processes, and generic processes. This step does not apply to application processes that are associated with application templates. This step runs on the server, gathers information about the specified resource, and then calls a specified plug-in step on an agent computer. To use this step, you must install a supported application server plug-in, such as the WebSphere® Application Server - Configure plug-in or the WebSphere Application Server - Deploy plug-in. For information about plug-ins, see [IBM UrbanCode™ Deploy Plug-ins](https://developer.ibm.com/urbancode/plugins/ibm-urbancode-deploy).

|Property|Description|
|--------|-----------|
|**Name**|A name for the step. Other process steps can refer to this step by this name.|
|**Resource**|The resource to use to store the configuration information that is retrieved from the application server.|
|**Plugin Step**|The plug-in step to run to retrieve the configuration information from the application server. If no plug-ins are installed that support the Update from Live Configuration process step, this list is empty.|

**Parent topic:** [Process steps: Reference](../topics/app_processSteps.md)

