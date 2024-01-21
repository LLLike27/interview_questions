# CSS 面试题

### 左侧定宽、中间自适应、右侧定宽，高度固定。如何布局？

- float 浮动实现
  - 清除浮动
- 绝对定位
- flex
- table
- grid

### 谈谈对盒子模型的认识

<img src="https://0122.vip/wp-content/uploads/2022/10/css-标准模型.jpg" alt="群聊天信息" width="320"/>

由内向外组成：

1. content
2. padding
3. border
4. margin

标准模型和IE模型的区别：宽高计算方式不同，标准模型就是content的宽度，不包括padding和border。

box-sizing: content-box：标准模型（默认）

box-sizing: border-box:  IE模型

### JS如何设置和获取盒模型的宽高

dom.style.width/height

### flex 常用属性

容器：

1. display: flex
2. align-items: center
3. justify-content: center
4. flex-driection:colomn | row’
5. flex-wrap: wrap
6. flex-flow: 分别是 flex-direction 和 flex-wrap的简写

子元素：

flex: 元素比例

flex-grow: 剩余宽/高度比例

### 伪类和伪元素的区别

伪类：

1. :active：元素处于活动状态时
2. :focus：元素已获取焦点时
3. :hover：元素处于悬浮状态时
4. :link：链接未访问时
5. :visited：链接已访问时
6. :first-child：元素是首个子元素时
7. :last-child：元素是最后一个子元素时
8. :nth-child()：元素是第 n 个子元素时
9. :nth-last-child()：元素是倒数第 n 个子元素时
10. :only-child：元素是唯一子元素时
11. :first-of-type：元素是首个特定类型的子元素时
12. :last-of-type：元素是最后一个特定类型的子元素时
13. :nth-of-type()：元素是第 n 个特定类型的子元素时
14. :nth-last-of-type()：元素是倒数第 n 个特定类型的子元素时
15. :only-of-type：元素是唯一的特定类型的子元素时
16. :not：不满足指定条件时
17. :target：元素 id 匹配到哈希值时
18. :root：元素是文档树的根元素时
19. :lang()：匹配到指定语言时
20. :empty：元素处于没有子元素状态时
21. :invalid 和 :valid：表单项是否有效
22. :required 和 :optional：表单项是否必填
23. :in-range和 :out-of-range：表单项是否超出范围
24. :read-only和 :read-write：表单项是否只读
25. :enabled和 :disabled：表单项是否禁用

伪元素：

1. ::first-letter：选中块状元素中的首字母
2. ::first-line：选中首行
3. ::before：在之前创建一个不在文档树中的元素
4. ::after：在之后创建一个不在文档树中的元素
5. ::placeholder：选中表单元素的占位文本
6. ::file-selector-button：选中类型为 file 的 input 里面的 button
7. ::selection：选中被用户高亮的部分⚠️注意兼容性
8. ::backdrop：选中视觉聚焦元素后面的背景元素⚠️注意兼容性
9. ::marker：选中 list 的 marker⚠️注意兼容性

### 什么是边距折叠

块的margin



### CSS选择器有哪些

1. 通配符选择器，* 是通配符，表示其下的样式对所有元素生效，但通配符的优先级较低。

2. id选择器，例如 #container

3. 类选择器，例如 .box

4. 标签选择器（类型选择器），例如 div span p 等元素标签，直接以标签名称作为样式选择器

5. 后代选择器，有层级关系的叠加样式选择器，是样式选择器的一种组合使用，例如 div p

6. 子选择器，例如 ul>li 或 div>p，对 ul 直接的子元素 li 设置样式，对 div 的直接子元素 p 设置样式。

7. 伪类选择器，例如 a:hover，当鼠标悬浮于 a 标签时的样式。

8. 伪元素选择器，例如常见的 ::before 和 ::after，单冒号写法也被现代浏览器支持（那是css2的语法）。

9. 相邻兄弟选择器，例如 img + p，样式将对 img 图片后面紧跟着的 p 段落生效。

10. 兄弟选择器，A~B 作用于 A 元素之后所有同层级 B 元素。

11. 属性选择器，通过已经存在的属性名或属性值匹配元素，例如 a[href="[example.org](https://link.juejin.cn?target=https%3A%2F%2Fexample.org)"] 或 a[title="一级标题"]。
