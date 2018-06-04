#### JS数据类型

string number boolean undefined null object symbol

#### typeof

```
// Numbers
typeof 37 === 'number';
typeof 3.14 === 'number';
typeof Math.LN2 === 'number';
typeof Infinity === 'number';
typeof NaN === 'number'; // 尽管NaN是"Not-A-Number"的缩写
typeof Number(1) === 'number'; // 但不要使用这种形式!

// Strings
typeof "" === 'string';
typeof "bla" === 'string';
typeof (typeof 1) === 'string'; // typeof总是返回一个字符串
typeof String("abc") === 'string'; // 但不要使用这种形式!

// Booleans
typeof true === 'boolean';
typeof false === 'boolean';
typeof Boolean(true) === 'boolean'; // 但不要使用这种形式!

// Symbols
typeof Symbol() === 'symbol';
typeof Symbol('foo') === 'symbol';
typeof Symbol.iterator === 'symbol';

// Undefined
typeof undefined === 'undefined';
typeof declaredButUndefinedVariable === 'undefined';
typeof undeclaredVariable === 'undefined'; 

// Objects
typeof {a:1} === 'object';

// 使用Array.isArray 或者 Object.prototype.toString.call
// 区分数组,普通对象
typeof [1, 2, 4] === 'object';

typeof new Date() === 'object';

// 下面的容易令人迷惑，不要使用！
typeof new Boolean(true) === 'object';
typeof new Number(1) === 'object';
typeof new String("abc") === 'object';

// 函数
typeof function(){} === 'function';
typeof class C{} === 'function'
typeof Math.sin === 'function';
typeof new Function() === 'function';
```

#### instanceof

`instanceof `运算符用来检测 `constructor.prototype `是否存在于参数 `object` 的原型链上。

```
function Cat(){}
Cat.prototype = {}
 
function Dog(){}
Dog.prototype ={}
 
var dog1 = new Dog();
alert(dog1 instanceof Dog);//true
alert(dog1 instanceof Object);//true
 
Dog.prototype = Cat.prototype;
alert(dog1 instanceof Dog);//false
alert(dog1 instanceof Cat);//false
alert(dog1 instanceof Object);//true;
 
var  dog2= new Dog();
alert(dog2 instanceof Dog);//true
alert(dog2 instanceof Cat);//true
alert(dog2 instanceof Object);//true
 
Dog.prototype = null;
var dog3 = new Dog();
alert(dog3 instanceof Cat);//false
alert(dog3 instanceof Object);//true
alert(dog3 instanceof Dog);//error
```

#### prototype

```
Object.prototype.toString.call(a) === '[object String]')
```

```
console.log(Object.prototype.toString.call(123))    //"[object Number]"
console.log(Object.prototype.toString.call('123'))    //"[object String]"
console.log(Object.prototype.toString.call(undefined))    //"[object Undefined]"
console.log(Object.prototype.toString.call(true))    //"[object Boolean]"
console.log(Object.prototype.toString.call(null))    //"[object Null]"
console.log(Object.prototype.toString.call({}))    //"[object Object]"
console.log(Object.prototype.toString.call([]))    //"[object Array]"
console.log(Object.prototype.toString.call(function(){}))    //"[object Function]"
```

#### constructor

注意： constructor 在类继承时会出错

```
c.constructor === Array
```



