#### Array对象方法

**length **数组中元素的数目

**POP 删除最后一项**

删除最后一项,并返回删除元素的值；如果数组为空则返回undefine

**shift 删除第一项**

删除原数组第一项，并返回删除元素的值；如果数组为空则返回undefine

**push 增加到最后**

并返回新数组长度；

**unshift增加到最前**

并返回新数组长度；

**reverse 数组翻转**

并返回翻转后的原数组，原数组翻转了

**join数组转成字符串**

并返回字符串，原数组木变

```
var a = [1,2,3,4,5]; 
var b=a.join('||');//b:"1||2||3||4||5" a:[1,2,3,4,5]
```

**indexOf数组元素索引**

并返回元素索引，不存在返回-1,索引从0开始

```
var a = ['a','b','c','d','e']; 
a.indexOf('a');//0
```

**slice截取\(切片\)数组 得到截取的数组**

返回从原数组中指定开始索引\(包含\)到结束索引\(不包含\)之间的项组成的新数组,原数组木变 ，索引从0开始

```
var a = ['a','b','c','d','e']; 
a.slice(1,3);//["b", "c"] a:['a','b','c','d','e']
```

**splice剪接数组 原数组变化 可以实现shift前删除，pop后删除,unshift前增加,同push后增加一样的效果**

返回剪接的元素数组,原数组变化 ，索引从0开始

```
var a = ['a','b','c','d','e'];
a.splice(0,0,88,99)//返回 [] 从第一个元素，截取长度0个 肯定是空 a:[88, 99, "a", "b", "c", "d", "e"] 同unshift前增加
```

**concat数组合并**

返回合并后的新数组,原数组不变

```
var a = ['a','b','c','d','e']; 
a.concat([88,99]);//["a", "b", "c", "d", "e", 88, 99]
```

**filter 过滤**

```
var arr = [
    {"name":"apple", "count": 2},
    {"name":"orange", "count": 5},
    {"name":"pear", "count": 3},
    {"name":"orange", "count": 16},
];
var newArr = arr.filter(function(item){
    return item.name === "orange";
});
 
console.log("Filter results:",newArr);
```

**reduce\(\) **可以实现一个累加器的功能，将数组的每个值（从左到右）将其降低到一个值。

```
//统计一个数组中有多少个不重复的单词
var arr = ["apple","orange","apple","orange","pear","orange"];
function getWordCnt(){
    return arr.reduce(function(prev,next){
        prev[next] = (prev[next] + 1) || 1;
        return prev;
    },{});
}
console.log(getWordCnt());
//reduce(callback, initialValue)会传入两个变量。回调函数(callback)和初始值(initialValue)
```

**find\(\)**方法返回数组中满足提供的测试函数的第一个元素的值。否则返回[`undefined`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/undefined)。

```
var inventory = [
  {name: 'apples', quantity: 2},
  {name: 'bananas', quantity: 0},
  {name: 'cherries', quantity: 5}
];
function findCherries(fruit) { 
  return fruit.name === 'cherries';
}
console.log(inventory.find(findCherries)); // { name: 'cherries', quantity: 5 }
```

  


#### 数组的遍历

![](https://pic4.zhimg.com/80/08235a5dafaaba6f9418704cba12fedd_hd.jpg)

