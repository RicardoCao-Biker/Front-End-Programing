### 原型

`array.push(num)`中push是沿着`array.__proto__`找到的，也就是Array.prototype.push

原型图

![](https://images2015.cnblogs.com/blog/787416/201603/787416-20160322110905589-2039017350.png)

![](https://pic1.zhimg.com/80/e83bca5f1d1e6bf359d1f75727968c11_hd.jpg)

### `__proto__`和`prototype`分别是什么？

* 方法的原型\(Function.prototype\)是对象

* 对象具有属性**proto**，可称为隐式原型，一个对象的隐式原型指向构造该对象的构造函数的原型，这也保证了实例能够访问在构造函数原型中定义的属性和方法。



