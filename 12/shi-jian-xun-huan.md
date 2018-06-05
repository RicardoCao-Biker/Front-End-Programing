#### JavaScript的单线程

JavaScript从诞生起就是单线程。原因大概是不想让浏览器变得太复杂，因为多线程需要共享资源、且有可能修改彼此的运行结果，对于一种网页脚本语言来说，这就太复杂了。后来就约定俗成，JavaScript为一种单线程语言。（Web Worker API可以实现多线程，但是JavaScript本身始终是单线程的。）

#### event loop事件循环

##### 概念

在程序中设置两个线程：一个负责程序本身的运行，称为"主线程"；另一个负责主线程与其他进程（主要是各种I/O操作）的通信，被称为"Event Loop线程"

##### 异步执行步骤

（1）所有同步任务都在主线程上执行，形成一个执行栈\(execution context stack）。

（2）主线程之外，还存在一个"任务队列"（task queue）。只要异步任务有了运行结果，就在"任务队列"之中放置一个事件。

（3）一旦"执行栈"中的所有同步任务执行完毕，系统就会读取"任务队列"，看看里面有哪些事件。那些对应的异步任务，于是结束等待状态，进入执行栈，开始执行。

（4）主线程不断重复上面的第三步。

#### JS的异步编程方法

* **callback回调函数**

```
function fn1 () {
  console.log('Function 1')
}

function fn2 () {
  setTimeout(() => {
    console.log('Function 2')
  }, 500)
}

function fn3 () {
  console.log('Function 3')
}
//执行顺序 ：F1 > F3 > F2
```

```
function fn2 (f) {
  setTimeout(() => {
    console.log('Function 2')
    f()
  }, 500)
}

fn2(fn3)
//可以通过callback使fn3在fn2后执行,达到F1 > F2 > F3的目的
```

* **事件发布/订阅**
* **Promise**

```
function fn1 () {
  console.log('Function 1')
}

function fn2 () {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      console.log('Function 2')
      resolve()
    }, 500)
  })
}

function fn3 () {
  console.log('Function 3')
}
```

```
fn1()
fn2().then(() => { fn3() })

// output : Function 1 > Function 2 > Function 3
```

* **async&await**

```
function fn1 () {
  console.log('Function 1')
}

function fn2 () {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      console.log('Function 2')
      resolve()
    }, 500)
  })
}

function fn3 () {
  console.log('Function 3')
}

async function asyncFunArr () {
  fn1()
  await fn2()
  fn3()
}

asyncFunArr()

// output : Function 1 > Function 2 > Function 3
```



