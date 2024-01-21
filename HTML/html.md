### 对语义化标签的理解，以及有哪些

语义化就是我们通过标签本身就知道标签所在代码的内容具有什么意义，即用使用特定的功能属性的标签做特定的事。比如使用 `h1` 标签我们就知道这是一个标题，使用 `header` 就知道这是页眉，使用 `footer` 就知道这是页脚。

优点：

1. 一是对机器友好。语义化功能让搜索引擎爬虫更有效地捕获页面结构，有利于SEO；利于页面结构分析，如识别文章标题，生成目录等等。

2. 二是对开发者友好。语义化让文档结构更清晰，便于整理和优化页面结构。

```html
<header> 页眉 </header>
<nav> 导航标记 </nav>
<section> 文档中的区段、小节 </section>
<main> 标签规定文档的主要内容区域 </main>
<article> 定义外部的内容，其中的内容独立于文档的其余部分。文章、评论等 </article>
<aside> 侧边栏 </aside>
<footer> 页脚 </footer>
<cite> 参考文献的引用 </cite>
<blockquote> 标签定义块引用 </blockquote>
<code> 代码片段 </code>
```

### 【高频】img 标签是块级元素吗？行内元素和块级元素有哪些？

行内元素：

span, a, i, br, img, button, input, label, select, textarea

b, big, small, tt, abbr, acronym, cite, code, dfn, em, kbd,

strong, samp, var, bdo, map, object, q, script, sub, sup

块级元素：

p, div, form, h1-h6, header, footer, ul, ol, table

address, article, aside, blockquote, dd, dl, fieldset, figcaption, figure, hgroup, hr, pre, section

img 还是可替换元素（replaced element）又称置换元素，所以与 span 不同可设置宽高。

**可替换元素：**

1. iframe
2. video
3. img
4. embed
