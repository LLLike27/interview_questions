### 为什么在v-for中使用key

key 主要作用在于给节点做唯一标识，以便高效的更新虚拟 DOM。 在新旧 nodes 对比时辨识 VNodes。如果不使用 key， Vue 会使用一种最大限度减少动态元素并且尽可能的尝试就地修改/复用相同类型元素的算法。 而使用 key 时，它会基于 key 的变化重新排列元素顺序，并且会移除 key 不存在的元素。

* 必须用key，且不能用index和random
* diff 算法中通过 tag 和 key 来判断，是否是 sameNode
* 减少渲染次数，提升渲染性能

### vue 组件如何通讯

* 父子组件 props 和 emit
* vuex、pinia
* 依赖、注入
* v-model
* $children $parent
* ref



### 描述组件渲染和更新的过程

创建组件：

1. 模板执行runder函数，触发响应式变量的getter
2. watcher 收集响应式变量依赖
3. watcher 监听到被更改时，触发模板渲染

数据更新：

1. 响应式数据触发 setter
2. setter 通知 watcher 数据更改
3. watcher 监听到，出发模板渲染

### 双向数据绑定 v-model 实现原理

v-model 其实就是语法糖，简写了 v-bind v-on(如input v-bind:value="value"， v-on:input)

### 对 mvvm 的理解

这里面可以分为三层，中间层就是vue，vue扮演了沟通的角色，它帮我们操作dom，接收我们处理的数据，被称为ViewModel。我们只需要描述html结构，和准备好对应的数据，vue帮我们做响应式处理。

### computed 有和特点

缓存，数据不会不会重新计算

### data 响应式数据为何是一个函数  👍

vue组件其实在编译后是一个类，在我们使用的时候其实是对它实例化，实例化的时候去执行data，如果data不是一个函数，多次实例化这个组件后，他们的data就会被共享了。相当于return一个函数，就是做了闭包，隔离了数据。

### ajax 请求应该放哪里

* beforeRouterEnter，在数据请求完成后再进入页面
* mounted，建议放此处，放created渲染比较混乱

### 用过 Vue.nextTick 吗，怎么理解

更改响应式状态时，最终的 DOM 更新并不是同步生效的， 而是由 Vue 将它们缓存在一个队列中，直到下一个“tick”才一起执行。 这样是为了确保每个组件无论发生多少状态改变，都仅执行一次更新。

理解：写在$nextTick当中的代码不会立即执行，而是等数据更新、DOM更新完成之后再执行， 如果你需要的操作，需要在数据和dom更新后才能进行，那么可以考虑使用$nextTick。 我简单的认为它是一个在最佳时机执行其回调的setTimeout函数。 这个最佳时机就是数据更新、DOM更新完成时刻。

### Vue2中，vue 的父组件的 mounted 和 子组件中的 mounted，哪个先执行？created呢？

**加载渲染：**
父beforeCreate -> 父created -> 父beforeMount -> 子beforeCreate 
-> 子created -> 子beforeMount -> 子mounted -> 父mounted

**子组件更新：**
父beforeUpdate -> 子beforeUpdate -> 子updated -> 父updated

**父组件更新：**
父beforeUpdate -> 父updated

**销毁：**
父beforeDestroy -> 子beforeDestroy -> 子destroyed -> 父destroyed
