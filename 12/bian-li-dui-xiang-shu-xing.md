## 遍历对象

### for in

主要用于遍历对象的可枚举属性，包括自有属性、继承自原型的属性

```
var obj = {"name":"Poly", "career":"it"}
Object.defineProperty(obj, "age", {value:"forever 18", enumerable:false});
Object.prototype.protoPer1 = function(){console.log("proto");};
Object.prototype.protoPer2 = 2;
console.log("For In : ");
for(var a in obj) console.log(a);
```

输出： name,carrer,protoPer1,protoPer2

### Object.keys

返回一个数组，元素均为对象自有的可枚举属性

```
var obj = {"name":"Poly", "career":"it"}
Object.defineProperty(obj, "age", {value:"forever 18", enumerable:false});
Object.prototype.protoPer1 = function(){console.log("proto");};
Object.prototype.protoPer2 = 2;
console.log("Object.keys:")
console.log(Object.keys(obj));
```

输出：name,career

### Object.getOwnProperty

用于返回对象的自有属性，包括可枚举和不可枚举的

```
var obj = {"name":"Poly", "career":"it"}
Object.defineProperty(obj, "age", {value:"forever 18", enumerable:false});
Object.prototype.protoPer1 = function(){console.log("proto");};
Object.prototype.protoPer2 = 2;
console.log("Object.getOwnPropertyNames: ");
console.log(Object.getOwnPropertyNames(obj));
```

输出：name,career,age

## 遍历数组

### forEach

```
var arr=[1,2,3,4];
arr.forEach(function(val, index) {
console.log(val, index);
});
```

### for in

```
var arr=["张三","李四","王五","赵六"];
for (var i in arr){
console.log(i,":",arr[i]);
```



