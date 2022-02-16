# 应用空间统计

> ![icon-note.gif](public_sys-resources/icon-note.gif) **说明：**
> 本模块首批接口从API version 8开始支持。后续版本的新增接口，采用上角标单独标记接口的起始版本。

## 导入模块

```js
import storagestatistics from "@ohos.storagestatistics";
```

## 系统能力

SystemCapability.FileManagement.StorageService.SpatialStatistics

## storagestatistics.getTotalSizeOfVolume

getTotalSizeOfVolume(volumeUuid: string): Promise&lt;number&gt;

异步获取指定卷的总空间大小，以promise方式返回。

- 参数

  | 参数名     | 类型   | 必填 | 说明 |
  | ---------- | ------ | ---- | ---- |
  | volumeUuid | string | 是   | 卷id |

- 返回值

  | 类型                  | 说明             |
  | --------------------- | ---------------- |
  | Promise&lt;number&gt; | 返回指定卷总空间 |

- 示例

  ```js
  let uuid = "";
  storagestatistics.getTotalSizeOfVolume(uuid).then(function(number){
      console.info("getTotalSizeOfVolume successfully:"+ number);
  }).catch(function(err){
      console.info("getTotalSizeOfVolume failed with error:"+ err);
  });
  ```

## storagestatistics.getTotalSizeOfVolume

getTotalSizeOfVolume(volumeUuid: string, callback:AsyncCallback&lt;number&gt;):void

异步获取指定卷的总空间大小，以callback方式返回。

- 参数

  | 参数名     | 类型                                 | 必填 | 说明                       |
  | ---------- | ------------------------------------ | ---- | -------------------------- |
  | volumeUuid | string                               | 是   | 卷id                       |
  | callback   | callback:AsyncCallback&lt;number&gt; | 是   | 获取指定卷总空间之后的回调 |

- 示例

  ```js
  let uuid = "";
  storagestatistics.getTotalSizeOfVolume(uuid, function(error, number){
      // do something
  });
  ```

  

## storagestatistics.getFreeSizeOfVolume

getFreeSizeOfVolume(volumeUuid: string): Promise&lt;number&gt;

异步获取指定卷的可用空间大小，以promise方式返回。

- 参数

  | 参数名     | 类型   | 必填 | 说明 |
  | ---------- | ------ | ---- | ---- |
  | volumeUuid | string | 是   | 卷id |

- 返回值

  | 类型                  | 说明               |
  | --------------------- | ------------------ |
  | Promise&lt;number&gt; | 返回指定卷可用空间 |

- 示例

  ```js
  let uuid = "";
  storagestatistics.getFreeSizeOfVolume(uuid).then(function(number){
      console.info("getFreeSizeOfVolume successfully:"+ number);
  }).catch(function(err){
      console.info("getFreeSizeOfVolume failed with error:"+ err);
  });
  
  ```

## storagestatistics.getFreeSizeOfVolume

getFreeSizeOfVolume(volumeUuid: string, callback:AsyncCallback&lt;number&gt;):void

异步获取指定卷的可用空间大小，以callback方式返回。

- 参数

  | 参数名     | 类型                                 | 必填 | 说明                         |
  | ---------- | ------------------------------------ | ---- | ---------------------------- |
  | volumeUuid | string                               | 是   | 卷id                         |
  | callback   | callback:AsyncCallback&lt;number&gt; | 是   | 获取指定卷可用空间之后的回调 |

- 示例

  ```js
  let uuid = "";
  storagestatistics.getFreeSizeOfVolume(uuid, function(error, number){
      // do something
  });
  ```

## storagestatistics.getBundleStats

getBundleStats(volumeUuid: string,  packageName:String, ): Promise&lt;BundleStats&gt;

异步获取指定卷上的应用存储状态，以promise方式返回。

- 参数

  | 参数名      | 类型   | 必填 | 说明     |
  | ----------- | ------ | ---- | -------- |
  | volumeUuid  | string | 是   | 卷id     |
  | packageName | string | 是   | 应用包名 |

- 返回值

  | 类型                                       | 说明                       |
  | ------------------------------------------ | -------------------------- |
  | Promise&lt;[Bundlestats](#bundlestats)&gt; | 返回指定卷上的应用存储状态 |

- 示例

  ```js
  let uuid = "";
  let packageName = "";
  storagestatistics.getBundleStats(uuid, packageName).then(function(BundleStats){
      console.info("getBundleStats successfully:"+ JSON.stringify(BundleStats));
  }).catch(function(err){
      console.info("getBundleStats failed with error:"+ err);
  });
  ```

## storagestatistics.getBundleStats

getBundleStats(volumeUuid: string, callback:AsyncCallback&lt;BundleStats&gt;):void

异步获取指定卷上的应用存储状态，以callback方式返回。

- 参数

  | 参数名     | 类型                                                      | 必填 | 说明                                 |
  | ---------- | --------------------------------------------------------- | ---- | ------------------------------------ |
  | volumeUuid | string                                                    | 是   | 卷id                                 |
  | callback   | callback:AsyncCallback&lt;[Bundlestats](#bundlestats)&gt; | 是   | 获取指定卷上的应用存储状态之后的回调 |

- 示例

  ```js
  let uuid = "";
  let packageName = "";
  storagestatistics.getBundleStats(uuid, packageName, function(error, BundleStats){
      // do something
  });
  ```

## BundleStats

### 属性

| 名称      | 类型   | 说明           |
| --------- | ------ | -------------- |
| appSize   | number | app数据大小    |
| cacheSize | number | 缓存数据大小   |
| dataSize  | number | 应用总数据大小 |