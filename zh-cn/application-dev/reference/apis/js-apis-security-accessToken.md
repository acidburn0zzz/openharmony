#  	访问控制管理

> ![icon-note.gif](public_sys-resources/icon-note.gif) **说明：**
> 本模块首批接口从API version 8开始支持。后续版本的新增接口，采用上角标单独标记接口的起始版本。

## 导入模块

```
import abilityAccessCtrl from '@ohos.abilityAccessCtrl'
```

## 系统能力
SystemCapability.Security.AccessToken

## abilityAccessCtrl.createAtManager

createAtManager(): AtManager

访问控制管理：获取访问控制模块对象。

- 返回值：
  | 类型 | 说明 |
  | -------- | -------- |
  | [AtManager](#atManager) | 获取访问控制模块的实例。 |

- 示例：
  ```
  var AtManager = abilityAccessCtrl.createAtManager();
  ```

## AtManager

管理访问控制模块的实例。

### verifyAccessToken

verifyAccessToken(tokenID: number, permissionName: string): Promise&lt;GrantStatus&gt;

校验应用是否授予权限，使用Promise方式异步返回结果。

- 参数：

  | 参数名   | 类型                 | 必填 | 说明                                       |
  | -------- | -------------------  | ---- | ------------------------------------------ |
  | tokenID   |  number   | 是   | 要校验的目标应用的身份标识。              |
  | permissionName | string | 是   | 需要校验的权限名称。 |

- 返回值：

  | 类型          | 说明                                |
  | :------------ | :---------------------------------- |
  | Promise&lt;GrantStatus&gt; | Promise实例，用于获取异步返回的授权状态结果。 |

- 示例：

  ```
  const AtManager = abilityAccessCtrl.createAtManager();
  let tokenID = 0;
  let promise = AtManager.verifyAccessToken(tokenID, "ohos.permission.GRANT_SENSITIVE_PERMISSIONS");
  promise.then(data => {
      console.log(`promise: data->${JSON.stringify(data)}`);
  });
  ```

### grantUserGrantedPermission

grantUserGrantedPermission(tokenID: number, permissionName: string, permissionFlag: number): Promise&lt;number&gt;

授予应用user grant权限，使用Promise方式异步返回结果。

需要权限：ohos.permission.GRANT_SENSITIVE_PERMISSIONS。

- 参数：

  | 参数名    | 类型                | 必填 | 说明                                                         |
  | --------- | ------------------- | ---- | ------------------------------------------------------------ |
  | tokenID      | number              | 是   | 目标应用的身份标识。            |
  | permissionName | string              | 是   | 被授予的权限名称。 |
  | permissionFlag  | number | 是   | 授权选项，1表示下次仍需弹窗，2表示允许、禁止后不再提醒，3表示系统授权不允许更改。  |

- 返回值：

  | 类型          | 说明                                |
  | :------------ | :---------------------------------- |
  | Promise&lt;number&gt; | Promise实例，用于获取异步返回的授权操作结果。 |
- 示例：

  ```
  const AtManager = abilityAccessCtrl.createAtManager();
  let tokenID = 0;
  let promise = AtManager.grantUserGrantedPermission(tokenID, "ohos.permission.GRANT_SENSITIVE_PERMISSIONS");
  promise.then(data => {
      console.log(`promise: data->${JSON.stringify(data)}`);
  });
  ```



### grantUserGrantedPermission

grantUserGrantedPermission(tokenID: number, permissionName: string, permissionFlag: number, callback: AsyncCallback&lt;number&gt;): void

授予应用user grant权限，使用callback回调异步返回结果。

需要权限：ohos.permission.GRANT_SENSITIVE_PERMISSIONS。

- 参数：

  | 参数名    | 类型                | 必填 | 说明                          |
  | --------- | ------------------- | ---- | ------------------------------------------------------------ |
  | tokenID      | number              | 是   | 目标应用的身份标识。           |
  | permissionName | string              | 是   | 被授予的权限名称。 |
  | permissionFlag  | number | 是   | 授权选项，1表示下次仍需弹窗，2表示允许、禁止后不再提醒，3表示系统授权不允许更改。  |
  | callback | AsyncCallback&lt;number&gt; | 是 | 检查授予应用user grant权限的操作结果同步的回调。 |

- 示例：

  ```
  const AtManager = abilityAccessCtrl.createAtManager();
  let tokenID = 0;
  let permissionFlag = 1;
  AtManager.grantUserGrantedPermission(tokenID, "ohos.permission.GRANT_SENSITIVE_PERMISSIONS",permissionFlag, data => {
      console.log(`callback: data->${JSON.stringify(data)}`);
  });
  ```

### revokeUserGrantedPermission

revokeUserGrantedPermission(tokenID: number, permissionName: string, permissionFlag: number): Promise&lt;number&gt;

撤销应用user grant权限，使用Promise方式异步返回结果。

需要权限：ohos.permission.REVOKE_SENSITIVE_PERMISSIONS。

- 参数：

  | 参数名    | 类型                | 必填 | 说明                                                         |
  | --------- | ------------------- | ---- | ------------------------------------------------------------ |
  | tokenID      | number              | 是   | 目标应用的身份标识。            |
  | permissionName | string              | 是   | 被撤销的权限名称。 |
  | permissionFlag  | number | 是   | 授权选项，1表示下次仍需弹窗，2表示允许、禁止后不再提醒，3表示系统授权不允许更改。  |

- 返回值：

  | 类型          | 说明                                |
  | :------------ | :---------------------------------- |
  | Promise&lt;number&gt; | Promise实例，用于获取异步返回的授权操作结果。 |

- 示例：

  ```
  const AtManager = abilityAccessCtrl.createAtManager();
  let tokenID = 0;
  let permissionFlag = 1;
  let promise = AtManager.revokeUserGrantedPermission(tokenID, "ohos.permission.GRANT_SENSITIVE_PERMISSIONS", permissionFlag);
  promise.then(data => {
      console.log(`promise: data->${JSON.stringify(data)}`);
  });
  ```

### revokeUserGrantedPermission

revokeUserGrantedPermission(tokenID: number, permissionName: string, permissionFlag: number, callback: AsyncCallback&lt;number&gt;): void

撤销应用user grant权限，使用callback回调异步返回结果。

需要权限：ohos.permission.REVOKE_SENSITIVE_PERMISSIONS。

- 参数：

  | 参数名    | 类型                | 必填 | 说明                          |
  | --------- | ------------------- | ---- | ------------------------------------------------------------ |
  | tokenID      | number              | 是   | 目标应用的身份标识。            |
  | permissionName | string              | 是   | 被撤销的权限名称。 |
  | permissionFlag  | number | 是   | 授权选项，1表示下次仍需弹窗，2表示允许、禁止后不再提醒，3表示系统授权不允许更改。  |
  | callback | AsyncCallback&lt;number&gt; | 是 | 检查撤销应用user grant权限的操作结果同步的回调。 |

- 示例：

  ```
  const AtManager = abilityAccessCtrl.createAtManager();
  let tokenID = 0;
  AtManager.revokeUserGrantedPermission(tokenID, "ohos.permission.GRANT_SENSITIVE_PERMISSIONS",permissionFlag, data => {
      console.log(`callback: data->${JSON.stringify(data)}`);
  });
  ```

### getPermissionFlags

getPermissionFlags(tokenID: number, permissionName: string): Promise&lt;number&gt;

获取指定应用的指定权限的flag，使用Promise方式异步返回结果。

- 参数：

  | 参数名    | 类型                | 必填 | 说明                          |
  | --------- | ------------------- | ---- | ------------------------------------------------------------ |
  | tokenID      | number              | 是   | 目标应用的身份标识。            |
  | permissionName | string              | 是   | 查询的权限名称。 |

- 返回值：

  | 类型          | 说明                                |
  | :------------ | :---------------------------------- |
  | Promise&lt;number&gt; | Promise实例，用于获取异步返回的查询结果。 |

- 示例：

  ```
  const AtManager = abilityAccessCtrl.createAtManager();
  let tokenID = 0;
  let promise = AtManager.getPermissionFlags(tokenID, "ohos.permission.GRANT_SENSITIVE_PERMISSIONS");
  promise.then(data => {
      console.log(`promise: data->${JSON.stringify(data)}`);
  });
  ```