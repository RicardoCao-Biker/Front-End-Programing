### 如何实现数组去重

```
Array.prototype.distinct = function(){
 var arr = this,
  result = [],
  i,
  j,
  len = arr.length;
 for(i = 0; i < len; i++){
  for(j = i + 1; j < len; j++){
   if(arr[i] === arr[j]){
    j = ++i;
   }
  }
  result.push(arr[i]);
 }
 return result;
}
var arra = [1,2,3,4,4,1,1,2,1,1,1];
arra.distinct();    //返回[3,4,2,1]
```

* Set去重

```
var arr = [1,2,2,3,4] // 需要去重的数组

var set = new Set(arr) // {1,2,3,4}
var newArr = Array.from(set) // 再把set转变成array

console.log(newArr) // [1,2,3,4]
```

* indexof方法

```
function unique(a) {
  var res = [];
  for (var i = 0, len = a.length; i < len; i++) {
    var item = a[i];
    (res.indexOf(item) === -1) && res.push(item);
  }
  return res;
}

var a = [1, 1, '1', '2', 1];
var ans = unique(a);
console.log(ans); // => [1, "1", "2"]
```



