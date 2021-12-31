# URI字符串解析

> ![icon-note.gif](public_sys-resources/icon-note.gif) **说明：**
> 本模块首批接口从API version 8开始支持。后续版本的新增接口，采用上角标单独标记接口的起始版本。


## 导入模块

```
import uri from '@ohos.uri'  
```


## 权限

无


## URI


### 属性

| 名称 | 参数类型 | 可读 | 可写 | 说明 |
| -------- | -------- | -------- | -------- | -------- |
| scheme | string | 是 | 否 | 获取URI&nbsp;的协议部分。 |
| userinfo | string | 是 | 否 | 获取&nbsp;URI&nbsp;的用户信息部分。 |
| host | string | 是 | 否 | 获取&nbsp;URI&nbsp;的主机名部分（不带端口）。 |
| port | string | 是 | 否 | 获取&nbsp;URI&nbsp;的端口部分。 |
| path | string | 是 | 否 | 获取&nbsp;URI&nbsp;的路径部分。 |
| query | string | 是 | 否 | 获取&nbsp;URI&nbsp;的查询部分。 |
| fragment | string | 是 | 否 | 获取&nbsp;URI&nbsp;的片段部分 |
| authority | string | 是 | 否 | 获取此URI的解码权限组件部分。 |
| ssp | string | 是 | 否 | 获取URI的解码方案特定部分。 |


### constructor

constructor(uri: string)

constructor是URI的构造函数。

- 参数：
  | 参数名 | 类型 | 可读 | 可写 | 说明 |
  | -------- | -------- | -------- | -------- | -------- |
  | url | string | 是 | 是 | 入参对象。 |

- 示例：
  ```
  var mm = 'http://username:password@host:8080/directory/file?foo=1&bar=2#fragment';
  new URI(mm); // Output 'http://username:password@host:8080/directory/file?foo=1&bar=2#fragment';
  new URI('http://username:password@host:8080'); // Output 'http://username:password@host:8080';
  ```


### toString

toString(): string

返回适用于URL中的查询字符串。

- 返回值：
  | 类型 | 说明 |
  | -------- | -------- |
  | string | 用于返回网址的字符串序列化。 |

- 示例:
  ```
  const url = new URL('http://username:password@host:8080/directory/file?query=pppppp#qwer=da');
  url.toString()
  ```


### equals

equals(other: URI): boolean

判断此URI是否与其他URI对象相等。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | other | [URI](#uri) | 是 | 需要比较的URI对象。 |

- 返回值：
  | 类型 | 说明 |
  | -------- | -------- |
  | boolean | 用于测试此URI是否与其他URI对象相等。 |

- 示例:
  ```
  const uri = new URI('http://username:password@host:8080/directory/file?query=pppppp#qwer=da');
  const uri1 = new URI('http://username:password@host:8080/directory/file?query=pppppp#qwer=da#fragment');
  uri.equals(uri1);
  ```


### checkIsAbsolute

判断此URI是否为绝对URI。

- 返回值：
  | 类型 | 说明 |
  | -------- | -------- |
  | boolean | 用于说明此URI是否为绝对URI（是否定义了scheme组件）。 |

- 示例:
  ```
  const uri = new URI('http://username:password@www.qwer.com:8080?query=pppppp');
  uri.checkIsAbsolute();
  ```


### normalize

normalize(): URI

规范化此URI的路径。

- 返回值：
  | 类型 | 说明 |
  | -------- | -------- |
  | URI | 用于规范化此URI的路径，并返回一个path被规范化后的URI对象。 |

- 示例:
  ```
  const uri = new URI('http://username:password@www.qwer.com:8080/path/path1/../path2/./path3?query=pppppp');
  let uri1 = uri.normalize();
  uri1.path;
  ```