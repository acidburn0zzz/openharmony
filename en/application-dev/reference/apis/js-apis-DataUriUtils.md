# DataUriUtils Module

## Modules to Import

```js
import dataUriUtils from '@ohos.ability.dataUriUtils';
```

## dataUriUtils.getId

getId(uri: string): number

Obtains the ID attached to the end of a given URI.

**Parameters**


| Name| Type| Mandatory| Description|
| ---- | ------ | ---- | --------------------------- |
| uri  | string | Yes| URI object from which the ID is to be obtained.|

**Return value**
| Type| Description|
| ------ | ------------------------ |
| number | ID obtained from the URI object.|

**Example**

```js
import dataUriUtils from '@ohos.ability.datauriutils'
dataUriUtils.getIdSync("com.example.dataUriUtils/1221")
```



## dataUriUtils.attachId

attachId(uri: string, id: number): string

Attaches an ID to the end of a given URI.

**Parameters**


| Name| Type| Mandatory| Description|
| ---- | ------ | ---- | --------------------------- |
| uri  | string | Yes| URI object to which an ID is to be attached.|
| id   | number | Yes| ID to be attached.|

**Return value**
| Type| Description|
| ------ | --------------------- |
| string | URI object with the ID attached.|

**Example**

```js
import dataUriUtils from '@ohos.ability.datauriutils'
var idint = 1122;
dataUriUtils.attachId(
    "com.example.dataUriUtils"
	idint,
)
```



## dataUriUtils.deleteId

deleteId(uri: string): string

Deletes the ID from the end of a given URI.

**Parameters**

| Name| Type| Mandatory| Description|
| ---- | ------ | ---- | --------------------------- |
| uri  | string | Yes| URI object from which the ID is to be deleted.|

**Return value**
| Type| Description|
| ------ | ------------------- |
| string | URI object with the ID deleted.|

**Example**

```js
import dataUriUtils from '@ohos.ability.datauriutils'
dataUriUtils.deleteId("com.example.dataUriUtils/1221")
```



## dataUriUtils.updateId

updateId(uri: string, id: number): string

Updates the ID in a given URI.

**Parameters**

| Name| Type| Mandatory| Description|
| ---- | ------ | ---- | ------------------- |
| uri  | string | Yes| URI object to be updated.|
| id   | number | Yes| New ID.|

**Return value**
| Type| Description|
| ------ | --------------- |
| string | URI object with the new ID.|

**Example**

```js
import dataUriUtils from '@ohos.ability.datauriutils'
var idint = 1122;
dataUriUtils.updateId(
    "com.example.dataUriUtils"
	idint,
)
```
