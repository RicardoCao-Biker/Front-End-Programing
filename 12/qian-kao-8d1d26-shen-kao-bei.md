#### 区别

浅复制只会将对象的各个属性进行依次复制，并不会进行递归复制，而 JavaScript 存储对象都是存地址的，所以浅复制会导致 obj.arr 和 shallowObj.arr 指向同一块内存地址,并没有开辟新的栈 .

深复制则不同，它不仅将原对象的各个属性逐个复制出去，而且将原对象各个属性所包含的对象也依次采用深复制的方法**递归复制**到新对象上

#### 浅拷贝

```
function copy(obj1) {
　　　　var obj2 = {};
　　　　for (var i in obj1) {
　　　　　　obj2[i] = obj1[i];
　　　　}
　　　　return obj2;
}
```

#### 深拷贝

* **通过递归复制**

```
  var china = {
	  	nation : '中国',
	  	birthplaces:['北京','上海','广州'],
	  	skincolr :'yellow',
	  	friends:['sk','ls']
   }
  //深复制，要想达到深复制就需要用递归
  function deepCopy(o,c){
    var c = c || {}
    for(var i in o){
    if(typeof o[i] === 'object'){
  	   //要考虑深复制问题了
          if(o[i].constructor === Array){
          //这是数组
          c[i] =[]
          }else{
          //这是对象
          c[i] = {}
          }
          deepCopy(o[i],c[i])
    }else{
	c[i] = o[i]
    }}
    return c
  }
  var result = {name:'result'}
  result = deepCopy(china,result)
  console.dir(result)
```

* **通过JSON**

```
  var test ={
	  	name:{
	  	 xing:{ 
	  	     first:'张',
	  	     second:'李'
	  	},
	  	ming:'老头'
	  },
	  age :40,
	  friend :['隔壁老王','宋经纪','同事']
	 }
  var result = JSON.parse(JSON.stringify(test))
  result.age = 30
  result.name.xing.first = '往'
  result.friend.push('fdagldf;ghad')
  console.dir(test)
  console.dir(result)
```



