### 原理简述

vue.js 则是采用数据劫持结合发布者-订阅者模式的方式，通过`Object.defineProperty()`来劫持各个属性的`setter`，`getter`，在数据变动时发布消息给订阅者，触发相应的监听回调。

### 实现流程

要实现mvvm的双向绑定，就必须要实现以下几点：

#### 1、实现一个数据监听器Observer，能够对数据对象的所有属性进行监听，如有变动可拿到最新值并通知订阅者

那么将需要observe的数据对象进行递归遍历

给这个对象的某个值赋值，就会触发`setter`,利用Obeject.defineProperty\(\)来监听属性变动

建立订阅者集合的数组，在setter中写入方法遍历并执行通知方法给所有的订阅者

#### 2、实现一个指令解析器Compile，对每个元素节点的指令进行扫描和解析，根据指令模板替换数据，以及绑定相应的更新函数

![](https://segmentfault.com/img/bVBQY3)

#### 3、实现一个Watcher，作为连接Observer和Compile的桥梁，能够订阅并收到每个属性变动的通知，执行指令绑定的相应回调函数，从而更新视图

1、在自身实例化时往属性订阅器\(dep\)里面添加自己

2、自身必须有一个update\(\)方法

3、待属性变动dep.notice\(\)通知时，能调用自身的update\(\)方法，并触发Compile中绑定的回调，则功成身退。

#### 4、mvvm入口函数，整合以上三者

![](https://segmentfault.com/img/bVBQYu)

  


