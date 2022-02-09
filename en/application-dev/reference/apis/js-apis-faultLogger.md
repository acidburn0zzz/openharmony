# Fault Logger
> ![icon-note.gif](public_sys-resources/icon-note.gif) **Note:**
> The initial APIs of this module are supported since API version 8. Newly added APIs will be marked with a superscript to indicate their earliest API version.

## Modules to Import

```
import faultLogger from '@ohos.faultLogger'
```

## Required Permissions

None

## faultLogger.FaultType

Enumerates the fault types.

| Name| Default Value| Description|
| -------- | -------- | -------- |
| NO_SPECIFIC | 0 | No specific fault type.|
| CPP_CRASH | 2 | C++ program crash.|
| JS_CRASH | 3 | JS program crash.|
| APP_FREEZE | 4 | Application freezing.|

## faultLogger.FaultLogInfo

Defines the data structure of the fault log information.

| Name| Type| Description|
| -------- | -------- | -------- |
| pid | number | Process ID of the faulty process.|
| uid | number | User ID of the faulty process.|
| type | [FaultType](#faultloggerfaulttype) | Fault type.|
| timestamp | number | Second-level timestamp when the log was generated.|
| reason | string | Reason for the fault.|
| module | string | Module on which the fault occurred.|
| summary | string | Summary of the fault.|
| fullLog | string | Full log text.|

## faultLogger.querySelfFaultLog

querySelfFaultLog(faultType: FaultType, callback: AsyncCallback&lt;Array&lt;FaultLogInfo&gt;&gt;) : void

Obtains the fault information about the current process. This method uses a callback to return the fault information array obtained, which contains a maximum of 10 pieces of fault information.

- Parameters
  | Name| Type| Mandatory| Description|
  | -------- | -------- | -------- | -------- |
  | faultType | [FaultType](#faultloggerfaulttype) | Yes| Fault type.|
  | callback | AsyncCallbackArray&lt;Array&lt;[FaultLogInfo](#faultloggerfaultloginfo)&gt;&gt; | Yes| Callback used to return the fault information array. <br/>The value is the fault information array obtained. If the value is **undefined**, an exception occurs during the information retrieval. In this case, an error string will be returned.

- Example
```
function queryFaultLogCallback(error, value) {
    if (error) {
        console.info('error is ' + error);
    } else {
        console.info("value length is " + value.length);
        let len = value.length;
        for (let i = 0; i < len; i++) {
            console.info("log: " + i);
            console.info("Log pid: " + value[i].pid);
            console.info("Log uid: " + value[i].uid);
            console.info("Log type: " + value[i].type);
            console.info("Log ts: " + value[i].ts);
            console.info("Log reason: " + value[i].reason);
            console.info("Log module: " + value[i].module);
            console.info("Log summary: " + value[i].summary);
            console.info("Log text: " + value[i].fullLog);
        }
    }
}
faultLogger.querySelfFaultLog(faultlogger.FaultType.JS_CRASH, queryFaultLogCallback);
```

## faultLogger.querySelfFaultLog

querySelfFaultLog(faultType: FaultType) : Promise&lt;Array&lt;FaultLogInfo&gt;&gt;;

Obtains the fault information about the current process. This method uses a promise to return the fault information array obtained, which contains a maximum of 10 pieces of fault information.

- Parameters
  | Name| Type| Mandatory| Description|
  | -------- | -------- | -------- | -------- |
  | faultType | [FaultType](#faultloggerfaulttype) | Yes| Fault type.|

- Return values
  | Type| Description|
  | -------- | -------- |
  | Promise&lt;Array&lt;[FaultLogInfo](#faultloggerfaultloginfo)&gt;&gt; | Promise used to return the fault information array. You can obtain the fault information instance in its **then()** method or use **await**. <br/>The value is the fault information array obtained. If the value is **undefined**, an exception occurs during the information retrieval.|

- Example
```
let value = await faultLogger.querySelfFaultLog(faultlogger.FaultType.JS_CRASH);
if (value) {
    console.info("value length is " + value.length);
    let len = value.length;
    for (let i = 0; i < len; i++) {
        console.info("log: " + i);
        console.info("Log pid: " + value[i].pid);
        console.info("Log uid: " + value[i].uid);
        console.info("Log type: " + value[i].type);
        console.info("Log ts: " + value[i].ts);
        console.info("Log reason: " + value[i].reason);
        console.info("Log module: " + value[i].module);
        console.info("Log summary: " + value[i].summary);
        console.info("Log text: " + value[i].fullLog);
    }
}
```