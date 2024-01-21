**type 和 interface**



使用上基本没有区别。



区别：

1. 官方文档：两者非常相似，在定义对象时，大部分情况可以任意选择使用
2. 官方文档：接口的几乎所有特性都可以在type使用
3. type可以定义基本类型，interface只能声明对象
4. type只能定义一次（不允许相同别名），interface多次声明会合并属性
5. interface可继承
6. interface可被class实现



总结：非对象类型一般使用type，对象类型一般使用interface（功能较多，为未来可能性）