# Apply to Live Configuration {#app_process_apply_live_config .concept}

This step is a wrapper step for applying configuration updates to an application server.

Applications, components, and generic processes share some process steps. This step applies to application processes, component processes, and generic processes. This step does not apply to application processes that are associated with application templates. This step runs on the server, gathers information about the specified resource, and then calls a specified plug-in step on an agent computer. To use this step, you must install a supported application server plug-in, such as the WebSphere® Application Server - Configure plug-in. For information about plug-ins, see [IBM UrbanCode™ Deploy Plug-ins](https://developer.ibm.com/urbancode/plugins/ibm-urbancode-deploy).

|Property|Description|
|--------|-----------|
|**Name**|A name for the step. Other process steps can refer to this step by this name.|
|**Resource**|The resource that contains the configuration information to apply to the application server.|
|**Plugin Step**|The plug-in step to run to apply the configuration to the application server. If no plug-ins are installed that support the Apply to Live Configuration process step, this list is empty.|

**Parent topic:** [Process steps: Reference](../topics/app_processSteps.md)

