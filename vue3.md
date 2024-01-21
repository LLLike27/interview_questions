### 组件通信

1. props $emit
2. expose ref
3. provide inject
4. vuex
5. v-model
6. $attrs

### vue2 和 vue3 的区别

1. vue3 新增 组合式api，同时兼容选项式api
2. 弃用 events api
3. 双向绑定：vue2 主要是采用数据劫持+发布订阅模式的方式，通过 es5 的 Object.defineProperty() 来劫持各个属性的setter，getter，在数据变动时发布消息给订阅者，触发相应监听回调。以及重写数组的方式实现的。 vue3 则使⽤了 es6 的 ProxyAPI 对数据代理，通过 reactive() 函数给每⼀个对象都包⼀层 Proxy， 通过 Proxy 监听属性的变化，从⽽实现对数据的监听。

4. vue2 要求模板中必须有一个根元素，而vue3则不再要求
5. 在 Vue 2 中，v-for 优先级比 v-if 高，Vue 3 中则相反，v-if 的优先级高于 v-for。

6. 生命周期改变
7. props 和 $emit
8. attrs 和 listeners  vue2 属性和事件分别是 attrs 和 listeners。vue3 只有attrs（包含了listeners），移除了 listeners
