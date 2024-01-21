**BFC**

块级格式化上下文：block formatting context



**创建条件**

1. float的值不为none
2. position的值不为static或者relative
3. display的值是inline-block、table-cell、flex、table-caption或者inline-flex
4. overflow的值不为visible



**作用**

1. margin 重叠问题
2. 解决高度塌陷的问题