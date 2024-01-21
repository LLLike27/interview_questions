**apply、call、bind、this 的认识**

apply、call、bind 都可以改变 this 的指向。

apply、call 类似，区别是参数不同。该方法的语法和作用与 apply() 方法类似，只有一个区别， 就是 call() 方法接受的是一个参数列表，而 apply() 方法接受的是一个包含多个参数的数组。

**this**

在 ES5 中，普通函数的 this 永远指向最后调用它的那个对象。this 的指向并不是在创建的时候就可以确定的。

另，可以简单的认为匿名函数的 this 永远指向 window。

箭头函数没有自己的this对象，其内部的this就是定义时上层作用域中的this（例如指向window）。