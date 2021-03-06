﻿# Create deviceManagementScriptState

> **Note:** Using the Microsoft Graph APIs to configure Intune controls and policies still requires that the Intune service is [correctly licensed](https://go.microsoft.com/fwlink/?linkid=839381) by the customer.

Create a new [deviceManagementScriptState](../resources/intune_devicefe_devicemanagementscriptstate.md) object.
## Prerequisites
One of the following **scopes** is required to execute this API:

*DeviceManagementManagedDevices.ReadWrite.All*
## HTTP Request
<!-- {
  "blockType": "ignored"
}
-->
```http
POST /deviceManagement/deviceManagementScripts/{deviceManagementScriptId}/runStates/
```

## Request headers
|Header|Value|
|---|---|
|Authorization|Bearer {token}. Required.|
|Accept|application/json|

## Request body
In the request body, supply a JSON representation of a deviceManagementScriptState object.
The following table shows the properties that are required when you create a deviceManagementScriptState.

|Property|Type|Description|
|---|---|---|
|id|String|Key of the device management script state entity.|
|runState|String|State of latest run of the device management script. Possible values are: `unknown`, `success`, `fail`.|
|resultMessage|String|Details of execution output.|
|lastStateUpdateDateTime|DateTimeOffset|Latest time the device management script executes.|



## Response
If successful, this method returns a `201 Created` response code and a [deviceManagementScriptState](../resources/intune_devicefe_devicemanagementscriptstate.md) object in the response body.

## Example
### Request
Here is an example of the request.
```http
POST https://graph.microsoft.com/beta/deviceManagement/deviceManagementScripts/{deviceManagementScriptId}/runStates/
Content-type: application/json
Content-length: 206

{
  "@odata.type": "#microsoft.graph.deviceManagementScriptState",
  "runState": "success",
  "resultMessage": "Result Message value",
  "lastStateUpdateDateTime": "2017-01-01T00:02:58.4418045-08:00"
}
```

### Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
```http
HTTP/1.1 201 Created
Content-Type: application/json
Content-Length: 255

{
  "@odata.type": "#microsoft.graph.deviceManagementScriptState",
  "id": "fbfa3cb8-3cb8-fbfa-b83c-fafbb83cfafb",
  "runState": "success",
  "resultMessage": "Result Message value",
  "lastStateUpdateDateTime": "2017-01-01T00:02:58.4418045-08:00"
}
```



