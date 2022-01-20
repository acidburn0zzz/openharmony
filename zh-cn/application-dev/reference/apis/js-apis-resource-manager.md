# 资源管理

> ![icon-note.gif](public_sys-resources/icon-note.gif) **说明：**
> 本模块首批接口从API version 7开始支持。后续版本的新增接口，采用上角标单独标记接口的起始版本。


## 导入模块

```
import resourceManager from '@ohos.resourceManager';
```


## 权限

无


## resourceManager.getResourceManager

getResourceManager(callback: AsyncCallback&lt;ResourceManager&gt;): void

获取当前应用的资源管理对象，使用callback形式返回ResourceManager对象。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | callback | AsyncCallback&lt;[ResourceManager](#resourcemanager)&gt; | 是 | callback方式返回ResourceManager对象 |

- 示例：
  ```
  resourceManager.getResourceManager((error, mgr) => {
      if (error != null) {
          console.log("error occurs" + error);
          return; 
      }
      mgr.getString(0x1000000, (error, value) => {
          if (error != null) {
              console.log(value);
          } else {
              console.log(value);
          }
      });
  });
  ```


## resourceManager.getResourceManager

getResourceManager(bundleName: string, callback: AsyncCallback&lt;ResourceManager&gt;): void

获取指定应用的资源管理对象，使用callback形式返回ResourceManager对象。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | bundleName | string | 是 | 指定应用的Bundle名称 |
  | callback | AsyncCallback&lt;[ResourceManager](#resourcemanager)&gt; | 是 | callback方式返回ResourceManager对象 |

- 示例：
  ```
  resourceManager.getResourceManager("com.example.myapplication", (error, mgr) => {
  });
  ```


## resourceManager.getResourceManager

getResourceManager(): Promise&lt;ResourceManager&gt;

获取当前应用的资源管理对象，使用Promise形式返回ResourceManager对象。

- 返回值：
  | 类型 | 说明 |
  | -------- | -------- |
  | Promise&lt;[ResourceManager](#resourcemanager)&gt; | Promise方式返回资源管理对象 |

- 示例：
  ```
  resourceManager.getResourceManager().then(mgr => {
      mgr.getString(0x1000000, (error, value) => {
          if (error != null) {
              console.log(value);
          } else {
              console.log(value);
          }
      });
  }).catch(error => {
      console.log(error);
  });
  ```


## resourceManager.getResourceManager

getResourceManager(bundleName: string): Promise&lt;ResourceManager&gt;

获取指定应用的资源管理对象，使用Promise形式返回ResourceManager对象。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | bundleName | string | 是 | 指定应用的Bundle名称 |

- 返回值：
  | 类型 | 说明 |
  | -------- | -------- |
  | Promise&lt;[ResourceManager](#resourcemanager)&gt; | Promise方式返回的资源管理对象 |

- 示例：
  ```
  resourceManager.getResourceManager("com.example.myapplication").then(mgr => {
  
  }).catch(error => {
  
  });
  ```


## Direction

用于表示设备屏幕方向。

| 名称 | 默认值 | 说明 |
| -------- | -------- | -------- |
| DIRECTION_VERTICAL | 0 | 竖屏 |
| DIRECTION_HORIZONTAL | 1 | 横屏 |


## DeviceType

用于表示当前设备类型。

| 名称 | 默认值 | 说明 |
| -------- | -------- | -------- |
| DEVICE_TYPE_PHONE | 0x00 | 手机 |
| DEVICE_TYPE_TABLET | 0x01 | 平板 |
| DEVICE_TYPE_CAR | 0x02 | 汽车 |
| DEVICE_TYPE_PC | 0x03 | 电脑 |
| DEVICE_TYPE_TV | 0x04 | 电视 |
| DEVICE_TYPE_WEARABLE | 0x06 | 穿戴 |


## ScreenDensity

用于表示当前设备屏幕密度。

| 名称 | 默认值 | 说明 |
| -------- | -------- | -------- |
| SCREEN_SDPI | 120 | 小规模的屏幕密度 |
| SCREEN_MDPI | 160 | 中规模的屏幕密度 |
| SCREEN_LDPI | 240 | 大规模的屏幕密度 |
| SCREEN_XLDPI | 320 | 特大规模的屏幕密度 |
| SCREEN_XXLDPI | 480 | 超大规模的屏幕密度 |
| SCREEN_XXXLDPI | 640 | 超特大规模的屏幕密度 |


## Configuration

表示当前设备的状态。


| 名称 | 参数类型 | 可读 | 可写 | 说明 |
| -------- | -------- | -------- | -------- | -------- |
| direction | [Direction](#direction) | 是 | 否 | 当前设备屏幕方向 |
| locale | string | 是 | 否 | 当前系统语言 |


## DeviceCapability

表示设备支持的能力。


| 名称 | 参数类型 | 可读 | 可写 | 说明 |
| -------- | -------- | -------- | -------- | -------- |
| screenDensity | [ScreenDensity](#screendensity) | 是 | 否 | 当前设备屏幕密度 |
| deviceType | [DeviceType](#devicetype) | 是 | 否 | 当前设备类型 |


## ResourceManager

提供访问应用资源的能力。

> ![icon-note.gif](public_sys-resources/icon-note.gif) **说明：**
> - ResourceManager涉及到的方法，仅限基于TS扩展的声明式开发范式使用。
> 
> - 资源文件在工程的resources目录中定义，id可通过$r(资源地址).id的方式获取，例如$r('app.string.test').id。


### getString

getString(resId: number, callback: AsyncCallback&lt;string&gt;): void

用户获取指定资源ID对应的字符串，使用callback形式返回字符串。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | resId | number | 是 | 资源ID值 |
  | callback | AsyncCallback&lt;string&gt; | 是 | 异步回调，用于返回获取的字符串 |

- 示例：
  ```
  resourceManager.getResourceManager((error, mgr) => {
      mgr.getString($r('app.string.test').id, (error, value) => {
          if (error != null) {
              console.log(value);
          } else {
              console.log(value);
          }
      });
  });
  ```


### getString

getString(resId: number): Promise&lt;string&gt;

用户获取指定资源ID对应的字符串，使用Promise形式返回字符串。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | resId | number | 是 | 资源ID值 |

- 返回值：
  | 类型 | 说明 |
  | -------- | -------- |
  | Promise&lt;string&gt; | 资源ID值对应的字符串 |

- 示例：
  ```
  resourceManager.getResourceManager((error, mgr) => {
      mgr.getString($r('app.string.test').id).then(value => {
          console.log(value);
      }).catch(error => {
          console.log("getstring promise " + error);
      });
  });
  ```


### getStringArray

getStringArray(resId: number, callback: AsyncCallback&lt;Array&lt;string&gt;&gt;): void

用户获取指定资源ID对应的字符串数组，使用callback形式返回字符串数组。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | resId | number | 是 | 资源ID值 |
  | callback | AsyncCallback&lt;Array&lt;string&gt;&gt; | 是 | 异步回调，用于返回获取的字符串数组 |

- 示例：
  ```
  resourceManager.getResourceManager((error, mgr) => {
      mgr.getStringArray($r('app.strarray.test').id, (error, value) => {
          if (error != null) {
              console.log(value);
          } else {
              console.log(value);
          }
      });
  });
  ```


### getStringArray

getStringArray(resId: number): Promise&lt;Array&lt;string&gt;&gt;

用户获取指定资源ID对应的字符串数组，使用Promise形式返回字符串数组。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | resId | number | 是 | 资源ID值 |

- 返回值：
  | 类型 | 说明 |
  | -------- | -------- |
  | Promise&lt;Array&lt;string&gt;&gt; | 资源ID值对应的字符串数组 |

- 示例：
  ```
  resourceManager.getResourceManager((error, mgr) => {
       mgr.getStringArray($r('app.strarray.test').id).then(value => {
          console.log(value);
      }).catch(error => {
          console.log("getstring promise " + error);
      });
  });
  ```


### getMedia

getMedia(resId: number, callback: AsyncCallback&lt;Uint8Array&gt;): void

用户获取指定资源ID对应的媒体文件内容，使用callback形式返回字节数组。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | resId | number | 是 | 资源ID值 |
  | callback | AsyncCallback&lt;Array&lt;Uint8Array&gt;&gt; | 是 | 异步回调，用于返回获取的媒体文件内容 |

- 示例：
  ```
  resourceManager.getResourceManager((error, mgr) => {
      mgr.getMedia($r('app.media.test').id, (error, value) => {
          if (error != null) {
              console.log(value);
          } else {
              console.log(value);
          }
      });
  });
  ```


### getMedia

getMedia(resId: number): Promise&lt;Uint8Array&gt;

用户获取指定资源ID对应的媒体文件内容，使用Promise形式返回字节数组。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | resId | number | 是 | 资源ID值 |

- 返回值：
  | 类型 | 说明 |
  | -------- | -------- |
  | Promise&lt;Array&lt;Uint8Array&gt;&gt; | 资源ID值对应的媒体文件内容 |

- 示例：
  ```
  resourceManager.getResourceManager((error, mgr) => {
      mgr.getMedia($r('app.media.test').id).then(value => {
          console.log(value);
      }).catch(error => {
          console.log("getstring promise " + error);
      });
  });
  ```


### getMediaBase64

getMediaBase64(resId: number, callback: AsyncCallback&lt;string&gt;): void

用户获取指定资源ID对应的图片资源Base64编码，使用callback形式返回字符串。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | resId | number | 是 | 资源ID值 |
  | callback | AsyncCallback&lt;string&gt; | 是 | 异步回调，用于返回获取的图片资源Base64编码 |

- 示例：
  ```
  resourceManager.getResourceManager((error, mgr) => {
      mgr.getMediaBase64($r('app.media.test').id, (error, value) => {
          if (error != null) {
              console.log(value);
          } else {
              console.log(value);
          }
      });
  });
  ```


### getMediaBase64

getMediaBase64(resId: number): Promise&lt;string&gt;

用户获取指定资源ID对应的图片资源Base64编码，使用Promise形式返回字符串。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | resId | number | 是 | 资源ID值 |

- 返回值：
  | 类型 | 说明 |
  | -------- | -------- |
  | Promise&lt;string&gt; | 资源ID值对应的图片资源Base64编码 |

- 示例：
  ```
  resourceManager.getResourceManager((error, mgr) => {
      mgr.getMediaBase64($r('app.media.test').id).then(value => {
          console.log(value);
      }).catch(error => {
          console.log("getstring promise " + error);
      });
  });
  ```


### getConfiguration

getConfiguration(callback: AsyncCallback&lt;Configuration&gt;): void

用户获取设备的Configuration，使用callback形式返回Configuration对象。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | callback | AsyncCallback&lt;[Configuration](#configuration)&gt; | 是 | 异步回调，用于返回设备的Configuration |

- 示例：
  ```
  resourceManager.getResourceManager((error, mgr) => {
      mgr.getConfiguration((error, value) => {
          if (error != null) {
              console.log(value);
          } else {
              console.log(value);
          }
      });
  });
  ```


### getConfiguration

getConfiguration(): Promise&lt;Configuration&gt;

用户获取设备的Configuration，使用Promise形式返回Configuration对象。

- 返回值：
  | 类型 | 说明 |
  | -------- | -------- |
  | Promise&lt;[Configuration](#configuration)&gt; | 设备的Configuration |

- 示例：
  ```
  resourceManager.getResourceManager((error, mgr) => {
      mgr.getConfiguration().then(value => {
          console.log(value);
      }).catch(error => {
          console.log("getstring promise " + error);
      });
  });
  ```


### getDeviceCapability

getDeviceCapability(callback: AsyncCallback&lt;DeviceCapability&gt;): void

用户获取设备的DeviceCapability，使用callback形式返回DeviceCapability对象。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | callback | AsyncCallback&lt;[DeviceCapability](#devicecapability)&gt; | 是 | 异步回调，用于返回设备的DeviceCapability |

- 示例：
  ```
  resourceManager.getResourceManager((error, mgr) => {
      mgr.getDeviceCapability((error, value) => {
          if (error != null) {
              console.log(value);
          } else {
              console.log(value);
          }
      });
  });
  ```


### getDeviceCapability

getDeviceCapability(): Promise&lt;DeviceCapability&gt;

用户获取设备的DeviceCapability，使用Promise形式返回DeviceCapability对象。

- 返回值：
  | 类型 | 说明 |
  | -------- | -------- |
  | Promise&lt;[DeviceCapability](#devicecapability)&gt; | 设备的DeviceCapability |

- 示例：
  ```
  resourceManager.getResourceManager((error, mgr) => {
      mgr.getDeviceCapability().then(value => {
          console.log(value);
      }).catch(error => {
          console.log("getstring promise " + error);
      });
  });
  ```


### getPluralString

getPluralString(resId: number, num: number, callback: AsyncCallback&lt;string&gt;): void

根据指定数量获取指定ID字符串表示的单复数字符串，使用callback形式返回字符串。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | resId | number | 是 | 资源ID值 |
  | num | number | 是 | 数量值 |
  | callback | AsyncCallback&lt;string&gt; | 是 | 异步回调，返回根据指定数量获取指定ID字符串表示的单复数字符串 |

- 示例：
  ```
  resourceManager.getResourceManager((error, mgr) => {
      mgr.getPluralString($r("app.plural.test").id, 1, (error, value) => {
          if (error != null) {
              console.log(value);
          } else {
              console.log(value);
          }
      });
  });
  ```


### getPluralString

getPluralString(resId: number, num: number): Promise&lt;string&gt;

根据指定数量获取对指定ID字符串表示的单复数字符串，使用Promise形式返回字符串。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | resId | number | 是 | 资源ID值 |
  | num | number | 是 | 数量值 |

- 返回值：
  | 类型 | 说明 |
  | -------- | -------- |
  | Promise&lt;string&gt; | 根据提供的数量获取对应ID字符串表示的单复数字符串 |

- 示例：
  ```
  resourceManager.getResourceManager((error, mgr) => {
      mgr.getPluralString($r("app.plural.test").id, 1).then(value => {
          console.log(value);
      }).catch(error => {
          console.log("getstring promise " + error);
      });
  });
  ```

### getRawFile<sup>8+</sup>

getRawFile(path: string, callback: AsyncCallback&lt;Uint8Array&gt;): void

用户获取指定路径对应的rawfile文件内容，使用callback形式返回字节数组。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | path | string | 是 | rawfile文件路径 |
  | callback | AsyncCallback&lt;Array&lt;Uint8Array&gt;&gt; | 是 | 异步回调，用于返回获取的rawfile文件内容 |

- 示例：
  ```
  resourceManager.getResourceManager((error, mgr) => {
      mgr.getRawFile("test.xml", (error, value) => {
          if (error != null) {
              console.log(value);
          } else {
              console.log(value);
          }
      });
  });
  ```

### getRawFile<sup>8+</sup>

getRawFile(path: string): Promise&lt;Uint8Array&gt;

用户获取指定路径对应的rawfile文件内容，使用Promise形式返回字节数组。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | path | string | 是 | rawfile文件路径 |

- 返回值：
  | 类型 | 说明 |
  | -------- | -------- |
  | Promise&lt;Array&lt;Uint8Array&gt;&gt; | rawfile文件内容 |

- 示例：
  ```
  resourceManager.getResourceManager((error, mgr) => {
      mgr.getRawFile("test.xml").then(value => {
          console.log(value);
      }).catch(error => {
          console.log("getrawfile promise " + error);
      });
  });
  ```