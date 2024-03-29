# DataAbilityHelper模块(JS端SDK接口)

## 导入模块

```
import featureAbility from '@ohos.ability.featureAbility'
import ohos_data_ability from '@ohos.data.dataability'
import ohos_data_rdb from '@ohos.data.rdb'
```

## DataAbilityHelper

### openFile

openFile(uri: string, mode: string, callback: AsyncCallback\<number>): void

在指定的远程路径中打开文件（callback形式）。

**参数：**

| 名称     | 类型                   | 必填 | 描述                               |
| -------- | ---------------------- | ---- | ---------------------------------- |
| uri      | string                 | 是   | 指示要打开的文件的路径。           |
| mode     | string                 | 是   | 指示文件打开模式‘rwt’。            |
| callback | AsyncCallback\<number> | 是   | 被指定的回调方法，返回文件描述符。 |

**示例：**

```javascript
import featureAbility from '@ohos.ability.featureAbility'
var DAHelper = featureAbility.acquireDataAbilityHelper(
    "dataability:///com.example.DataAbility"
);
var mode = "rwt";
DAHelper.openFile(
    "dataability:///com.example.DataAbility",
    mode,
    (err) => {
		console.info("==========================>Called=======================>");
});
```

### openFile

openFile(uri: string, mode: string): Promise\<number>

**参数：**

| 名称 | 类型   | 必填 | 描述                     |
| ---- | ------ | ---- | ------------------------ |
| uri  | string | 是   | 指示要打开的文件的路径。 |
| mode | string | 是   | 指示文件打开模式‘rwt’。  |

**返回值：**
| 类型             | 说明             |
| ---------------- | ---------------- |
| Promise\<number> | 返回文件描述符。 |

**示例：**

```javascript
import featureAbility from '@ohos.ability.featureAbility'
var DAHelper = featureAbility.acquireDataAbilityHelper(
    "dataability:///com.example.DataAbility"
);
var mode = "rwt";
DAHelper.openFile(
    "dataability:///com.example.DataAbility"，
    mode).then((void) => {
		console.info("==========================>openFileCallback=======================>");
});
```

### on('dataChange')

on(type: 'dataChange', uri: string, callback: AsyncCallback\<void>): void

注册观察者以观察给定uri指定的数据callback通知。

**参数：**

| 名称     | 类型                 | 必填 | 描述                     |
| -------- | -------------------- | ---- | ------------------------ |
| type     | string               | 是   | 数据更改。               |
| uri      | string               | 是   | 指示要操作的数据的路径。 |
| callback | AsyncCallback\<void> | 是   | 指示数据更改时的回调。   |

**示例：**

```js
import featureAbility from '@ohos.ability.featureAbility'
var helper = featureAbility.acquireDataAbilityHelper(
    "dataability:///com.example.DataAbility"
);
function onChangeNotify() {
    console.info("==========================>onChangeNotify=======================>");
};
helper.on(
    "dataChange",
    "dataability:///com.example.DataAbility",
    onChangeNotify
)
```

### off('dataChange')

off(type: 'dataChange', uri: string, callback?: AsyncCallback\<void>): void

注消观察者以停止观察给定uri指定的数据callback通知。

**参数：**

| 名称     | 类型                 | 必填 | 描述                     |
| -------- | -------------------- | ---- | ------------------------ |
| type     | string               | 是   | 数据更改。               |
| uri      | string               | 是   | 指示要操作的数据的路径。 |
| callback | AsyncCallback\<void> | 否   | 指示已注册的回调。       |

**示例：**

```js
import featureAbility from '@ohos.ability.featureAbility'
var helper = featureAbility.acquireDataAbilityHelper(
    "dataability:///com.example.DataAbility"
);
function onChangeNotify() {
    console.info("==========================>onChangeNotify=======================>");
};
helper.off(
    "dataChange",
    "dataability:///com.example.DataAbility",
)
helper.off(
    "dataChange",
    "dataability:///com.example.DataAbility",
    onChangeNotify
)
```

### getType

getType(uri: string, callback: AsyncCallback\<string>): void

获取给定URI指定数据的MIME类型（callback形式）。

**参数：**

| 名称     | 类型                   | 必填 | 描述                                          |
| -------- | ---------------------- | ---- | --------------------------------------------- |
| uri      | string                 | 是   | 指示要操作的数据的路径。                      |
| callback | AsyncCallback\<string> | 是   | 回调方法，返回与uri指定的数据匹配的MIME类型。 |

**示例：**

```js
import featureAbility from '@ohos.ability.featureAbility'
var DAHelper = featureAbility.acquireDataAbilityHelper(
    "dataability:///com.example.DataAbility"
);
DAHelper.getType(
    "dataability:///com.example.DataAbility",
    (err, data) => {
		console.info("==========================>Called=======================>");
});
```

### getType

getType(uri: string): Promise\<string>

获取给定URI指定数据的MIME类型（Promise形式）。

**参数：**

| 名称 | 类型   | 必填 | 描述                     |
| ---- | ------ | ---- | ------------------------ |
| uri  | string | 是   | 指示要操作的数据的路径。 |

**返回值：**
| 类型             | 说明                                |
| ---------------- | ----------------------------------- |
| Promise\<string> | 返回与uri指定的数据匹配的MIME类型。 |

**示例：**

```js
import featureAbility from '@ohos.ability.featureAbility'
var DAHelper = featureAbility.acquireDataAbilityHelper(
    "dataability:///com.example.DataAbility"
);
DAHelper.getType(
    "dataability:///com.example.DataAbility"
	).then((data) => {
		console.info("==========================>getTypeCallback=======================>");
});
```

### getFileTypes

getFileTypes(uri: string, mimeTypeFilter: string, callback: AsyncCallback<Array\<string>>): void

获取支持的文件的MIME类型（callback形式）。

**参数：**

| 名称           | 类型                           | 必填 | 描述                               |
| -------------- | ------------------------------ | ---- | ---------------------------------- |
| uri            | string                         | 是   | 指示要获取的文件的路径。           |
| mimeTypeFilter | string                         | 是   | 指示要获取的文件的MIME类型。       |
| callback       | AsyncCallback\<Array\<string>> | 是   | 回调方法，返回匹配的MIME类型数组。 |

**示例：**

```js
import featureAbility from '@ohos.ability.featureAbility'
var DAHelper = featureAbility.acquireDataAbilityHelper(
    "dataability:///com.example.DataAbility"
);
DAHelper.getFileTypes(
    "dataability:///com.example.DataAbility",
    "image/*",
    (err, data) => {
		console.info("==========================>Called=======================>");
});
```



### getFileTypes

getFileTypes(uri: string, mimeTypeFilter: string): Promise\<Array\<string>>

获取支持的文件的MIME类型（Promise形式）。

**参数：**

| 名称           | 类型   | 必填 | 描述                         |
| -------------- | ------ | ---- | ---------------------------- |
| uri            | string | 是   | 指示要获取的文件的路径。     |
| mimeTypeFilter | string | 是   | 指示要获取的文件的MIME类型。 |

**返回值：**
| 类型                     | 说明                     |
| ------------------------ | ------------------------ |
| Promise\<Array\<string>> | 返回匹配的MIME类型数组。 |

**示例：**

```js
import featureAbility from '@ohos.ability.featureAbility'
var DAHelper = featureAbility.acquireDataAbilityHelper(
    "dataability:///com.example.DataAbility"
);
DAHelper.getFileTypes(
    "dataability:///com.example.DataAbility",
    "image/*"
	).then((data) => {
		console.info("==========================>getFileTypesCallback=======================>");
});
```

### normalizeUri

normalizeUri(uri: string, callback: AsyncCallback\<string>): void

将引用数据功能的给定uri转换为规范化uri（callback形式）。

**参数：**

| 名称     | 类型                   | 必填 | 描述                                                         |
| -------- | ---------------------- | ---- | ------------------------------------------------------------ |
| uri      | string                 | 是   | 指示要规范化的uri对象。                                      |
| callback | AsyncCallback\<string> | 是   | 回调方法。如果数据功能支持uri规范化或null，则返回规范化uri对象。 |

**示例：**

```js
import featureAbility from '@ohos.ability.featureAbility'
var DAHelper = featureAbility.acquireDataAbilityHelper(
    "dataability:///com.example.DataAbility"
);
DAHelper.normalizeUri(
    "dataability:///com.example.DataAbility",
    (err, data) => {
		console.info("==========================>Called=======================>");
});
```

### normalizeUri

normalizeUri(uri: string): Promise\<string>

将引用数据功能的给定uri转换为规范化uri（Promise形式）。

**参数：**

| 名称 | 类型   | 必填 | 描述                    |
| ---- | ------ | ---- | ----------------------- |
| uri  | string | 是   | 指示要规范化的uri对象。 |

**返回值：**
| 类型             | 说明                                                   |
| ---------------- | ------------------------------------------------------ |
| Promise\<string> | 如果数据功能支持uri规范化或null，则返回规范化uri对象。 |

**示例：**

```js
import featureAbility from '@ohos.ability.featureAbility'
var DAHelper = featureAbility.acquireDataAbilityHelper(
    "dataability:///com.example.DataAbility"
);
DAHelper.normalizeUri(
    "dataability:///com.example.DataAbility",
	).then((data) => {
		console.info("==========================>normalizeUriCallback=======================>");
});
```

### denormalizeUri

denormalizeUri(uri: string, callback: AsyncCallback\<string>): void

将由normalizeUri（uri）生成的给定规范化uri转换为非规范化uri（callback形式）。

**参数：**

| 名称     | 类型                   | 必填 | 描述                                                |
| -------- | ---------------------- | ---- | --------------------------------------------------- |
| uri      | string                 | 是   | 指示要规范化的uri对象。                             |
| callback | AsyncCallback\<string> | 是   | 回调方法。如果反规范化成功，则返回反规范化uri对象。 |

**示例：**

```js
import featureAbility from '@ohos.ability.featureAbility'
var DAHelper = featureAbility.acquireDataAbilityHelper(
    "dataability:///com.example.DataAbility"
);
DAHelper.denormalizeUri(
    "dataability:///com.example.DataAbility",,
    (err, data) => {
		console.info("==========================>Called=======================>");
});
```



### denormalizeUri

denormalizeUri(uri: string): Promise\<string>

将由normalizeUri（uri）生成的给定规范化uri转换为非规范化uri（Promise形式）。

**参数：**

| 名称 | 类型   | 必填 | 描述                    |
| ---- | ------ | ---- | ----------------------- |
| uri  | string | 是   | 指示要规范化的uri对象。 |

**返回值：**
| 类型             | 说明                                      |
| ---------------- | ----------------------------------------- |
| Promise\<string> | 如果反规范化成功，则返回反规范化uri对象。 |

**示例：**

```js
import featureAbility from '@ohos.ability.featureAbility'
var DAHelper = featureAbility.acquireDataAbilityHelper(
    "dataability:///com.example.DataAbility"
);
DAHelper.denormalizeUri(
    "dataability:///com.example.DataAbility",
	).then((data) => {
		console.info("==========================>denormalizeUriCallback=======================>");
});
```

### notifyChange

notifyChange(uri: string, callback: AsyncCallback\<void>): void

通知已注册的观察者uri指定的数据资源的更改（callback形式）。

**参数：**

| 名称     | 类型                 | 必填 | 描述                     |
| -------- | -------------------- | ---- | ------------------------ |
| uri      | string               | 是   | 指示要操作的数据的路径。 |
| callback | AsyncCallback\<void> | 是   | 回调方法。               |

**示例：**

```js
import featureAbility from '@ohos.ability.featureAbility'
var helper = featureAbility.acquireDataAbilityHelper(
    "dataability:///com.example.DataAbility"
);
helper.notifyChange(
    "dataability:///com.example.DataAbility",,
    (err) => {
		console.info("==========================>Called=======================>");
});
```

### notifyChange

notifyChange(uri: string): Promise\<void>

通知已注册的观察者uri指定的数据资源的更改（Promise形式）。

**参数：**

| 名称 | 类型   | 必填 | 描述                     |
| ---- | ------ | ---- | ------------------------ |
| uri  | string | 是   | 指示要操作的数据的路径。 |

**返回值：**
| 类型           | 说明                  |
| -------------- | --------------------- |
| Promise\<void> | 返回值为Promise对象。 |

**示例：**

```js
import featureAbility from '@ohos.ability.featureAbility'
var DAHelper = featureAbility.acquireDataAbilityHelper(
    "dataability:///com.example.DataAbility"
);
DAHelper.notifyChange(
    "dataability:///com.example.DataAbility",
	).then((void) => {
		console.info("==========================>notifyChangeCallback=======================>");
});
```

### insert

insert(uri: string, valuesBucket: rdb.ValuesBucket, callback: AsyncCallback\<number>): void

将单个数据记录插入数据库（callback形式）。

**参数：**

| 名称         | 类型                   | 必填 | 描述                                                   |
| ------------ | ---------------------- | ---- | ------------------------------------------------------ |
| uri          | string                 | 是   | 指示要插入的数据的路径。                               |
| valuesBucket | rdb.ValuesBucket       | 是   | 指示要插入的数据记录。如果此参数为空，将插入一个空行。 |
| callback     | AsyncCallback\<number> | 是   | 回调方法，返回插入数据记录的索引。                     |

**示例：**

```js
import featureAbility from '@ohos.ability.featureAbility'
var DAHelper = featureAbility.acquireDataAbilityHelper(
    "dataability:///com.example.DataAbility"
);
const valueBucket = {
    "name": "rose",
    "age": 22,
    "salary": 200.5,
    "blobType": u8,
}
DAHelper.insert(
    "dataability:///com.example.DataAbility",
    valueBucket,
    (err, data) => {
		console.info("==========================>Called=======================>");
});
```

### insert

insert(uri: string, valuesBucket: rdb.ValuesBucket): Promise\<number>

将单个数据记录插入数据库（Promise形式）。

**参数：**

| 名称         | 类型             | 必填 | 描述                                                   |
| ------------ | ---------------- | ---- | ------------------------------------------------------ |
| uri          | string           | 是   | 指示要插入的数据的路径。                               |
| valuesBucket | rdb.ValuesBucket | 是   | 指示要插入的数据记录。如果此参数为空，将插入一个空行。 |

**返回值：**
| 类型             | 说明                     |
| ---------------- | ------------------------ |
| Promise\<number> | 返回插入数据记录的索引。 |

**示例：**

```js
import featureAbility from '@ohos.ability.featureAbility'
var DAHelper = featureAbility.acquireDataAbilityHelper(
    "dataability:///com.example.DataAbility"
);
const valueBucket = {
    "name": "rose1",
    "age": 221,
    "salary": 20.5,
    "blobType": u8,
}
DAHelper.insert(
    "dataability:///com.example.DataAbility",
    valueBucket
	).then((data) => {
		console.info("==========================>insertCallback=======================>");
});
```

### batchInsert

batchInsert(uri: string, valuesBuckets: Array<rdb.ValuesBucket>, callback: AsyncCallback\<number>): void

插入数据库（callback形式）。

**参数：**

| 名称         | 类型                    | 必填 | 描述                             |
| ------------ | ----------------------- | ---- | -------------------------------- |
| uri          | string                  | 是   | 指示要插入的数据的路径。         |
| valuesBucket | Array<rdb.ValuesBucket> | 是   | 指示要插入的数据记录。           |
| callback     | AsyncCallback\<number>  | 是   | 回调方法。返回插入的数据记录数。 |

**示例：**

```js
import featureAbility from '@ohos.ability.featureAbility'
var DAHelper = featureAbility.acquireDataAbilityHelper(
    "dataability:///com.example.DataAbility"
);
var cars = new Array({"name": "roe11", "age": 21, "salary": 20.5, "blobType": u8,},
                     {"name": "roe12", "age": 21, "salary": 20.5, "blobType": u8,},
                     {"name": "roe13", "age": 21, "salary": 20.5, "blobType": u8,})
DAHelper.batchInsert(
    "dataability:///com.example.DataAbility",
    cars,
    (err, data) => {
		console.info("==========================>Called=======================>");
});
```

### batchInsert

batchInsert(uri: string, valuesBuckets: Array<rdb.ValuesBucket>): Promise\<number>

将多个数据记录插入数据库（Promise形式）。

**参数：**

| 名称         | 类型                    | 必填 | 描述                     |
| ------------ | ----------------------- | ---- | ------------------------ |
| uri          | string                  | 是   | 指示要插入的数据的路径。 |
| valuesBucket | Array<rdb.ValuesBucket> | 是   | 指示要插入的数据记录。   |

**返回值：**
| 类型             | 说明                   |
| ---------------- | ---------------------- |
| Promise\<number> | 返回插入的数据记录数。 |

**示例：**

```js
import featureAbility from '@ohos.ability.featureAbility'
var DAHelper = featureAbility.acquireDataAbilityHelper(
    "dataability:///com.example.DataAbility"
);
var cars = new Array({"name": "roe11", "age": 21, "salary": 20.5, "blobType": u8,},
                     {"name": "roe12", "age": 21, "salary": 20.5, "blobType": u8,},
                     {"name": "roe13", "age": 21, "salary": 20.5, "blobType": u8,})
DAHelper.batchInsert(
    "dataability:///com.example.DataAbility",
    cars
	).then((data) => {
		console.info("==========================>batchInsertCallback=======================>");
});
```

### delete

delete(uri: string, predicates: dataAbility.DataAbilityPredicates, callback: AsyncCallback\<number>): void

从数据库中删除一个或多个数据记录（callback形式）。

**参数：**

| 名称         | 类型                              | 必填 | 描述                                             |
| ------------ | --------------------------------- | ---- | ------------------------------------------------ |
| uri          | string                            | 是   | 指示要删除的数据的路径。                         |
| valuesBucket | dataAbility.DataAbilityPredicates | 是   | 指示筛选条件。当此参数为null时，应定义处理逻辑。 |
| callback     | AsyncCallback\<number>            | 是   | 回调方法。返回已删除的数据记录数。               |

**示例：**

```js
import featureAbility from '@ohos.ability.featureAbility'
import ohos_data_ability from '@ohos.data.dataability'
var DAHelper = featureAbility.acquireDataAbilityHelper(
    "dataability:///com.example.DataAbility"
);
let da = new ohos_data_ability.DataAbilityPredicates()
DAHelper.delete(
    "dataability:///com.example.DataAbility",
    da,
    (err, data) => {
		console.info("==========================>Called=======================>");
});
```

### delete

delete(uri: string, predicates: dataAbility.DataAbilityPredicates): Promise\<number>

从数据库中删除一个或多个数据记录（Promise形式）。

**参数：**

| 名称         | 类型                              | 必填 | 描述                                             |
| ------------ | --------------------------------- | ---- | ------------------------------------------------ |
| uri          | string                            | 是   | 指示要删除的数据的路径。                         |
| valuesBucket | dataAbility.DataAbilityPredicates | 是   | 指示筛选条件。当此参数为null时，应定义处理逻辑。 |

**返回值：**
| 类型             | 说明                     |
| ---------------- | ------------------------ |
| Promise\<number> | 返回已删除的数据记录数。 |

**示例：**

```js
import featureAbility from '@ohos.ability.featureAbility'
var DAHelper = featureAbility.acquireDataAbilityHelper(
    "dataability:///com.example.DataAbility"
);
let da = new ohos_data_ability.DataAbilityPredicates()
DAHelper.delete(
    "dataability:///com.example.DataAbility",
    da
	).then((data) => {
		console.info("==========================>deleteCallback=======================>");
});
```

### update

update(uri: string, valuesBucket: rdb.ValuesBucket, predicates: dataAbility.DataAbilityPredicates, callback: AsyncCallback\<number>): void

更新数据库中的数据记录（callback形式）。

**参数：**

| 名称         | 类型                              | 必填 | 描述                                             |
| ------------ | --------------------------------- | ---- | ------------------------------------------------ |
| uri          | string                            | 是   | 指示要更新的数据的路径。                         |
| valuesBucket | rdb.ValuesBucket                  | 是   | 指示要更新的数据。                               |
| predicates   | dataAbility.DataAbilityPredicates | 是   | 指示筛选条件。当此参数为null时，应定义处理逻辑。 |
| callback     | AsyncCallback\<number>            | 是   | 回调方法，返回更新的数据记录数。                 |

**示例：**

```js
import featureAbility from '@ohos.ability.featureAbility'
import ohos_data_ability from '@ohos.data.dataability'
var DAHelper = featureAbility.acquireDataAbilityHelper(
    "dataability:///com.example.DataAbility"
);
const va = {
    "name": "roe1",
    "age": 21,
    "salary": 20.5,
    "blobType": u8,
}
let da = new ohos_data_ability.DataAbilityPredicates()
DAHelper.update(
    "dataability:///com.example.DataAbility",
    va,
    da,
    (err, data) => {
		console.info("==========================>Called=======================>");
});
```

### update

update(uri: string, valuesBucket: rdb.ValuesBucket, predicates: dataAbility.DataAbilityPredicates): Promise\<number>

更新数据库中的数据记录（Promise形式）。

**参数：**

| 名称         | 类型                              | 必填 | 描述                                             |
| ------------ | --------------------------------- | ---- | ------------------------------------------------ |
| uri          | string                            | 是   | 指示要更新的数据的路径。                         |
| valuesBucket | rdb.ValuesBucket                  | 是   | 指示要更新的数据。                               |
| predicates   | dataAbility.DataAbilityPredicates | 是   | 指示筛选条件。当此参数为null时，应定义处理逻辑。 |

**返回值：**
| 类型             | 说明                                         |
| ---------------- | -------------------------------------------- |
| Promise\<number> | 返回值为Promise对象，Promise中包含应用信息。 |

**示例：**

```js
import featureAbility from '@ohos.ability.featureAbility'
import ohos_data_ability from '@ohos.data.dataability'
var DAHelper = featureAbility.acquireDataAbilityHelper(
    "dataability:///com.example.DataAbility"
);
const va = {
    "name": "roe1",
    "age": 21,
    "salary": 20.5,
    "blobType": u8,
}
let da = new ohos_data_ability.DataAbilityPredicates()
DAHelper.update(
    "dataability:///com.example.DataAbility",
    va,
    da
	).then((data) => {
		console.info("==========================>updateCallback=======================>");
});
```

### query

query(uri: string, columns: Array\<string>, predicates: dataAbility.DataAbilityPredicates, callback: AsyncCallback\<ResultSet>): void

查询数据库中的数据（callback形式）。

**参数：**

| 名称       | 类型                              | 必填 | 描述                                             |
| ---------- | --------------------------------- | ---- | ------------------------------------------------ |
| uri        | string                            | 是   | 指示要查询的数据的路径。                         |
| columns    | rdb.ValuesBucket                  | 是   | 指示要查询的列。如果此参数为空，则查询所有列。   |
| predicates | dataAbility.DataAbilityPredicates | 是   | 指示筛选条件。当此参数为null时，应定义处理逻辑。 |
| callback   | AsyncCallback\<ResultSet>         | 是   | 回调方法，返回查询结果。                         |

**示例：**

```js
import featureAbility from '@ohos.ability.featureAbility'
import ohos_data_ability from '@ohos.data.dataability'
var DAHelper = featureAbility.acquireDataAbilityHelper(
    "dataability:///com.example.DataAbility"
);
var cars=new Array({"value1"}, {"value2"}, {"value3"}, {"value4"});
let da = new ohos_data_ability.DataAbilityPredicates()
DAHelper.query(
    "dataability:///com.example.DataAbility",
    cars,
    da,
    (err, data) => {
		console.info("==========================>Called=======================>");
});
```



### query

query(uri: string, columns: Array\<string>, predicates: dataAbility.DataAbilityPredicates): Promise\<ResultSet>

查询数据库中的数据（Promise形式）。

**参数：**

| 名称       | 类型                              | 必填 | 描述                                             |
| ---------- | --------------------------------- | ---- | ------------------------------------------------ |
| uri        | string                            | 是   | 指示要查询的数据的路径。                         |
| columns    | rdb.ValuesBucket                  | 是   | 指示要查询的列。如果此参数为空，则查询所有列。   |
| predicates | dataAbility.DataAbilityPredicates | 是   | 指示筛选条件。当此参数为null时，应定义处理逻辑。 |

**返回值：**
| 类型                | 说明           |
| ------------------- | -------------- |
| Promise\<ResultSet> | 返回查询结果。 |

**示例：**

```js
import featureAbility from '@ohos.ability.featureAbility'
import ohos_data_ability from '@ohos.data.dataability'
var DAHelper = featureAbility.acquireDataAbilityHelper(
    "dataability:///com.example.DataAbility"
);
var cars=new Array({"value1"}, {"value2"}, {"value3"}, {"value4"});
let da = new ohos_data_ability.DataAbilityPredicates()
DAHelper.query(
    "dataability:///com.example.DataAbility",
    cars,
    da
	).then((data) => {
		console.info("==========================>queryCallback=======================>");
});
```