### promise 的理解

概念：异步操作的一种解决方案，一般用来解决层层嵌套的回调函数（回调地狱 callback hell）的问题。

**async** **await** 语法是 ES7出现的，是基于ES6的 promise和generator实现的

### 手写 Promise

不使用 构造函数 constructor(es6) 实现简单的promise

```js
function promise(fn) {
  this.type = 'pending'
  this.result = ''
  this.resolve = function(d) {
    this.type = 'resolved'
    this.result = d
  }
  this.reject = function(err) {
    this.type = 'rejected'
    this.result = err
  }
  fn(this.resolve.bind(this), this.reject.bind(this))
  return this
}
promise.prototype.then = function(onResolve, onReject) {
  if (this.type === 'resolved') {
    onResolve(this.result)
  } else {
    onReject(this.result)
  }
}

new promise((resolve, reject) => {
  reject('data')
}).then((d) => {
  console.log('resolve', d)
}, (err) => {
  console.log('reject', err)
})
```

### 什么是事件循环

事件循环指的是js代码所在运行环境（浏览器、nodejs）编译器的一种解析执行规则。事件循环不属于js代码本身的范畴，而是属于js编译器的范畴，在js中讨论事件循环是没有意义的。换句话说，js代码可以理解为是一个人在公司中具体做的事情， 而 事件循环 相当于是公司的一种规章制度。 两者不是一个层面的概念。

**微任务、宏任务概念介绍：**

1. 微任务与宏任务就属于js代码的范畴
2. js代码主要分为两大类： 同步代码、异步代码
3. 异步代码又分为：微任务与宏任务

**宏任务：**事件、ajax、定时器、文件读取

**微任务：**Promise.then、async/await

**事件循环Event Loop执行机制：**

- 1.进入到script标签,就进入到了第一次事件循环.
- 2.遇到同步代码，立即执行
- 3.遇到宏任务,放入到宏任务队列里.
- 4.遇到微任务,放入到微任务队列里.
- 5.执行完所有同步代码
- 6.执行微任务代码
- 7.微任务代码执行完毕，本次队列清空
- 寻找下一个宏任务，重复步骤1
  - 以此反复直到清空所以宏任务，这种不断重复的执行机制，就叫做事件循环

### 迭代器

迭代器是帮助我们对某个数据结构进行遍历的对象, 它有一个 next 方法, next 方法返回一个对象

```js
const items = ["zero", "one", "two"]; 
const it = items[Symbol.iterator]();  
it.next(); 
// {value: "zero", done: false} 
it.next(); 
// {value: "one", done: false} 
it.next(); 
// {value: "two", done: false} 
it.next(); 
// {value: undefined, done: true}
```



### 原型链

js语言当中，大体可以归类为两种数据类型，一种是普通值类型，另一种是对象。比如我们创建一个数组，数组自身除了我们自己创建的属性之外，还有各种方法和属性。它的方法从哪里来呢，就是从数组继承而来的。它就保存在_proto_ 里面里面，如果我们要进行数组合并，这时它本身肯定是没有这个属性的，它就会从原型链上找，在proto 中就能找到 concat 方法。

就是一层一层往上proto上找。

### 继承



### 内存泄露

js 内存泄漏通常是由于一些不再需要的引用没有及时清理，以及死循环等逻辑缺陷形成的堆栈溢出导致的。 例如已经不用的全局变量、定时器、闭包等未能及时解除引用，一些类似死循环或没必要的高频执行等逻辑缺陷。

- 意外的全局变量

- 被遗忘的定时器和回调函数

- 弃用的DOM节点资源

- 不当使用的闭包

- 堆栈溢出

  

### js 中的作用域

作用域的分类：全局作用域、函数作用域、块级作用域。

作用域的作用：具有隔离变量的作用，所以不同作用域的同名变量不会冲突。

### apply、call、bind、this 的认识

apply、call、bind 都可以改变 this 的指向。

apply、call 类似，区别是参数不同。该方法的语法和作用与 apply() 方法类似，只有一个区别， 就是 call() 方法接受的是一个参数列表，而 apply() 方法接受的是一个包含多个参数的数组。

**this**

在 ES5 中，普通函数的 this 永远指向最后调用它的那个对象。this 的指向并不是在创建的时候就可以确定的。

另，可以简单的认为匿名函数的 this 永远指向 window。

箭头函数没有自己的this对象，其内部的this就是定义时上层作用域中的this（例如指向window）。

### new 关键字背后的操作

new 运算符创建一个用户定义的对象类型的实例或具有构造函数的内置对象的实例。

new 关键字会进行如下的操作：

- 1.创建一个空的js 对象（即**{}**）；
- 2.为步骤 1 新创建的对象添加属性***\*proto\****，将该属性链接至构造函数的原型对象；
- 3.将步骤 1 新创建的对象作为**this**的上下文 ；
- 4.如果构造函数没有显式返回一个对象，则返刚创建的对象（即绑定的this）。

### 数据类型与赋值

7中数据类型：Undefined、 Null、 Boolean、 Number、 String、 Symbol（es6）、 BigInt（es2020）

8：Object
