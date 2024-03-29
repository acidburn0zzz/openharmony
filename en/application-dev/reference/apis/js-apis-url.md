# URL String Parsing

> ![](../../public_sys-resources/icon-note.gif) **Note:**
> The initial APIs of this module are supported since API version 7. Newly added APIs will be marked with a superscript to indicate their earliest API version.


## Modules to Import

```
import Url from '@ohos.url' 
```


## Required Permissions

None


## URLSearchParams


### constructor

constructor(init?: string[][] | Record&lt;string, string&gt; | string | URLSearchParams)

Creates a **URLSearchParams** instance.

- Parameters
  | Name| Type| Mandatory| Description|
  | -------- | -------- | -------- | -------- |
  | init | string[][]&nbsp;\|&nbsp;Record&lt;string,&nbsp;string&gt;&nbsp;\|&nbsp;string&nbsp;\|&nbsp;URLSearchParams | No| Input parameter objects, which include the following: <br/>-&nbsp;**string[][]**: two-dimensional string array<br/>-&nbsp;**Record&lt;string,&nbsp;string&gt;**: list of objects<br/>-&nbsp;**string**: string<br/>-&nbsp;**URLSearchParams**: object|

- Example
  ```
  var objectParams = new URLSearchParams([ ['user1', 'abc1'], ['query2', 'first2'], ['query3', 'second3'] ]);
  var objectParams1 = new URLSearchParams({"fod" : 1 , "bard" : 2});
  var objectParams2 = new URLSearchParams('?fod=1&bard=2');
  var urlObject = new URL('https://developer.mozilla.org/?fod=1&bard=2');
  var params = new URLSearchParams(urlObject .search);
  ```


### append

append(name: string, value: string): void

Appends a key-value pair into the query string.

- Parameters
  | Name| Type| Mandatory| Description|
  | -------- | -------- | -------- | -------- |
  | name | string | Yes| Key of the key-value pair to append.|
  | value | string | Yes| Value of the key-value pair to append.|

- Example
  ```
  let urlObject = new URL('https://developer.exampleUrl/?fod=1&bard=2');
  let paramsObject = new URLSearchParams(urlObject.search.slice(1));
  paramsObject.append('fod', 3);
  ```


### delete

delete(name: string): void

Deletes key-value pairs of the specified key.

- Parameters
  | Name| Type| Mandatory| Description|
  | -------- | -------- | -------- | -------- |
  | name | string | Yes| Key of the key-value pairs to delete.|

- Example
  ```
  let urlObject = new URL('https://developer.exampleUrl/?fod=1&bard=2');
  let paramsobject = new URLSearchParams(urlObject.search.slice(1));
  paramsobject.delete('foo');
  ```


### getAll

getAll(name: string): string[]

Obtains all the key-value pairs based on the specified key.

- Parameters
  | Name| Type| Mandatory| Description|
  | -------- | -------- | -------- | -------- |
  | name | string | Yes| Key specified to obtain all key-value pairs.|

- Return values
  | Type| Description|
  | -------- | -------- |
  | string[] | All key-value pairs matching the specified key.|

- Example
  ```
  let urlObject = new URL('https://developer.exampleUrl/?fod=1&bard=2'); 
  let paramsObject = new URLSearchParams(urlObject.search.slice(1)); 
  paramsObject.append('fod', 3); // Add a second value for the foo parameter.
  console.log(params.getAll('fod')) // Output ["1","3"].
  ```


### entries

entries(): IterableIterator&lt;[string, string]&gt;

Obtains an ES6 iterator. Each item of the iterator is a JavaScript array, and the first and second fields of each array are the key and value respectively.

- Return values
  | Type| Description|
  | -------- | -------- |
  | IterableIterator&lt;[string,&nbsp;string]&gt; | An ES6 iterator.|

- Example
  ```
  var searchParamsObject = new URLSearchParams("keyName1=valueName1&keyName2=valueName2"); 
  for (var pair of searchParamsObject .entries()) { // Show keyName/valueName pairs
      console.log(pair[0]+ ', '+ pair[1]);
  }
  ```


### forEach

forEach(callbackfn: (value: string, key: string, searchParams: Object) =&gt; void, thisArg?: Object): void

Traverses the key-value pairs in the **URLSearchParams** instance by using a callback.

- Parameters
  | Name| Type| Mandatory| Description|
  | -------- | -------- | -------- | -------- |
  | callbackfn | function | Yes| Callback invoked to traverse the key-value pairs in the **URLSearchParams** instance.|
  | thisArg | Object | No| Value to use when the callback is invoked.|

  **Table 1** callbackfn parameter description
  
  | Name| Type| Mandatory| Description|
  | -------- | -------- | -------- | -------- |
  | value | string | Yes| Value that is currently traversed.|
  | key | string | Yes| Key that is currently traversed.|
  | searchParams | Object | Yes| Instance that invokes the **forEach** method.|

- Example
  ```
  const myURLObject = new URL('https://developer.exampleUrl/?fod=1&bard=2'); 
  myURLObject.searchParams.forEach((value, name, searchParams) => {  
      console.log(name, value, myURLObject.searchParams === searchParams);
  });
  ```


### get

get(name: string): string | null

Obtains the value of the first key-value pair based on the specified key.

- Parameters
  | Name| Type| Mandatory| Description|
  | -------- | -------- | -------- | -------- |
  | name | string | Yes| Key specified to obtain the value.|

- Return values
  | Type| Description|
  | -------- | -------- |
  | string | Returns the value of the first key-value pair if obtained.|
  | null | Returns null if no value is obtained.|

- Example
  ```
  var paramsOject = new URLSearchParams(document.location.search.substring(1)); 
  var name = paramsOject.get("name"); // is the string "Jonathan" 
  var age = parseInt(paramsOject.get("age"), 10); // is the number 18
  var address = paramsOject.get("address"); // null
  ```


### has

has(name: string): boolean

Checks whether a key has a value.
- Parameters
  | Name| Type| Mandatory| Description|
  | -------- | -------- | -------- | -------- |
  | name | string | Yes| Key specified to search for its value.|

- Return values
  | Type| Description|
  | -------- | -------- |
  | boolean | Returns **true** if the value exists; returns **false** otherwise.|

- Example
  ```
  let urlObject = new URL('https://developer.exampleUrl/?fod=1&bard=2');
  let paramsObject = new URLSearchParams(urlObject.search.slice(1)); 
  paramsObject.has('bard') === true;
  ```


### set

set(name: string, value: string): void

Sets the value for a key. If key-value pairs matching the specified key exist, the value of the first key-value pair will be set to the specified value and other key-value pairs will be deleted. Otherwise, the key-value pair will be appended to the query string.

- Parameters
  | Name| Type| Mandatory| Description|
  | -------- | -------- | -------- | -------- |
  | name | string | Yes| Key of the value to set.|
  | value | string | Yes| Value to set.|

- Example
  ```
  let urlObject = new URL('https://developer.exampleUrl/?fod=1&bard=2');
  let paramsObject = new URLSearchParams(urlObject.search.slice(1));
  paramsObject.set('baz', 3); // Add a third parameter.
  ```


### sort

sort(): void


Sorts all key-value pairs contained in this object based on the Unicode code points of the keys and returns undefined. This method uses a stable sorting algorithm, that is, the relative order between key-value pairs with equal keys is retained.


- Example
  ```
  var searchParamsObject = new URLSearchParams("c=3&a=9&b=4&d=2"); // Create a test URLSearchParams object
  searchParamsObject.sort(); // Sort the key/value pairs
  console.log(searchParamsObject.toString()); // Display the sorted query string // Output a=9&b=2&c=3&d=4
  ```


### keys

keys(): IterableIterator&lt;string&gt;


Obtains an ES6 iterator that contains the keys of all the key-value pairs.


- Return values
  | Type| Description|
  | -------- | -------- |
  | IterableIterator&lt;string&gt; | ES6 iterator that contains the keys of all the key-value pairs.|


- Example
  ```
  var searchParamsObject = new URLSearchParams("key1=value1&key2=value2"); // Create a URLSearchParamsObject object for testing
  for (var key of searchParamsObject .keys()) { // Output key-value pairs
      console.log(key);
  }
  ```


### values

values(): IterableIterator&lt;string&gt;

Obtains an ES6 iterator that contains the values of all the key-value pairs.

- Return values
  | Type| Description|
  | -------- | -------- |
  | IterableIterator&lt;string&gt; | ES6 iterator that contains the values of all the key-value pairs.|

- Example
  ```
  var searchParams = new URLSearchParams("key1=value1&key2=value2"); // Create a URLSearchParamsObject object for testing
  for (var value of searchParams.values()) { 
      console.log(value);
  }
  ```


### [Symbol.iterator]

[Symbol.iterator](): IterableIterator&lt;[string, string]&gt;


Obtains an ES6 iterator. Each item of the iterator is a JavaScript array, and the first and second fields of each array are the key and value respectively.


- Return values
  | Type| Description|
  | -------- | -------- |
  | IterableIterator&lt;[string,&nbsp;string]&gt; | An ES6 iterator.|


- Example
  ```
  const paramsObject = new URLSearchParams('fod=bay&edg=bap');
  for (const [name, value] of paramsObject) { 
      console.log(name, value); 
  } 
  ```


### tostring

toString(): string


Obtains search parameters that are serialized as a string and, if necessary, percent-encodes the characters in the string.


- Return values
  | Type| Description|
  | -------- | -------- |
  | string | String of serialized search parameters, which is percent-encoded if necessary.|


- Example
  ```
  let url = new URL('https://developer.exampleUrl/?fod=1&bard=2');
  let params = new URLSearchParams(url.search.slice(1)); 
  params.append('fod', 3);
  console.log(params.toString());
  ```


## URL


### Attributes

| Name| Type| Readable| Writable| Description|
| -------- | -------- | -------- | -------- | -------- |
| hash | string | Yes| Yes| String that contains a harsh mark (#) followed by the fragment identifier of a URL.|
| host | string | Yes| Yes| Host information in a URL.|
| hostname | string | Yes| Yes| Hostname (without the port) in a URL.|
| href | string | Yes| Yes| String that contains the whole URL.|
| origin | string | Yes| No| Read-only string that contains the Unicode serialization of the origin of the represented URL.|
| password | string | Yes| Yes| Password in a URL.|
| pathname | string | Yes| Yes| Path in a URL.|
| port | string | Yes| Yes| Port in a URL.|
| protocol | string | Yes| Yes| Protocol in a URL.|
| search | string | Yes| Yes| Serialized query string in a URL.|
| searchParams | URLsearchParams | Yes| No| **URLSearchParams** object allowing access to the query parameters in a URL.|
| username | string | Yes| Yes| Username in a URL.|


### constructor

constructor(url: string, base?: string | URL)


Creates a URL.


- Parameters
  | Name| Type| Mandatory| Description|
  | -------- | -------- | -------- | -------- |
  | url | string | Yes| Input object.|
  | base | string&nbsp;\|&nbsp;URL | No| Input parameter, which can be any of the following: <br/>-&nbsp;**string**: string<br/>-&nbsp;**URL**: string or object|


- Example
  ```
  var mm = 'http://username:password@host:8080';
  var a = new URL("/", mm); // Output 'http://username:password@host:8080/';
  var b = new URL(mm); // Output 'http://username:password@host:8080/';
  new URL('path/path1', b); // Output 'http://username:password@host:8080/path/path1';
  var c = new URL('/path/path1', b);  // Output 'http://username:password@host:8080/path/path1'; 
  new URL('/path/path1', c); // Output 'http://username:password@host:8080/path/path1';
  new URL('/path/path1', a); // Output 'http://username:password@host:8080/path/path1';
  new URL('/path/path1', "https://www.exampleUrl/fr-FR/toto"); // Output https://www.exampleUrl/path/path1
  new URL('/path/path1', ''); // Raises a TypeError exception as '' is not a valid URL
  new URL('/path/path1'); // Raises a TypeError exception as '/path/path1' is not a valid URL
  new URL('http://www.shanxi.com', ); // Output http://www.shanxi.com/
  new URL('http://www.shanxi.com', b); // Output http://www.shanxi.com/
  ```


### tostring

toString(): string

Converts the parsed URL into a string.


- Return values
  | Type| Description|
  | -------- | -------- |
  | string | Website address in a serialized string.|


- Example
  ```
  const url = new URL('http://username:password@host:8080/directory/file?query=pppppp#qwer=da');
  url.toString()
  ```


### toJSON

toJSON(): string


Converts the parsed URL into a JSON string.


- Return values
  | Type| Description|
  | -------- | -------- |
  | string | Website address in a serialized string.|


- Example
  ```
  const url = new URL('http://username:password@host:8080/directory/file?query=pppppp#qwer=da');
  url.toJSON()
  ```
