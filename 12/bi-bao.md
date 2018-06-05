#### 作用域

##### 原则

ES5中没有块级作用域，只有函数作用域和全局作用域

每次定义一个函数，都会产生一个作用域链（scope chain）。当JavaScript寻找变量varible时（这个过程称为变量解析），总会优先在当前作用域链的第一个对象中查找属性varible ，如果找到，则直接使用这个属性；否则，继续查找下一个对象的是否存在这个属性。

#### 闭包

##### 概念

闭包是指可以访问另一个函数作用域变量的函数，一般是定义在外层函数中的内层函数

##### 意义

局部变量无法共享和长久的保存，而全局变量可能造成变量污染，所以我们希望有一种机制既可以长久的保存变量又不会造成全局污染。

##### 特点

占用更多内存，不容易被释放

##### 使用

```
function createAdder(){
  var n=0
  return function(){
  n += 1
  console.log(n)
  }
}
let adder = createAdder()
adder() //1
adder() //2
console.log(n) // n is not undefined
```





