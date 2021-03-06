### 概念

根据具体内容，选择合适的HTML标签进行代码的编写。

HTML标签不仅要使机器、SEO易于理解，也要使人易于理解。

### 意义

* 清晰的页面结构。去掉或样式丢失的时候,也能让页面呈现清晰的结构，增强页面的可读性。
* 支持更多的设备。屏幕阅读器会完全根据你的标记来“读”你的网页。更好的支持浏览器的阅读模式等。
* 有利于SEO。和搜索引擎建立良好沟通，有助于爬虫抓取更多的有效信息，搜索引擎的爬虫也依赖于标记来确定上下文和各个关键字的权重。
* 便于团队开发和维护。在团队中大家都遵循同一个标准，可以减少很多差异化的东西，方便开发和维护，提高开发效率，甚至实现模块化开发。

### 使用

#### HTML标签的语义化

* **文本内容**

| 标签名 | 英文全拼 | 中文翻译 |
| :---: | :---: | :---: |
| &lt;p&gt; | paragraph | 段落 |
| &lt;blockquote&gt; | block quotation | 块级引用 |
| &lt;hr&gt; | horizontal rule | 水平分割线 |
| &lt;ul&gt; | unordered list | 无序列表 |
| &lt;ol&gt; | ordered list | 有序列表 |
| &lt;li&gt; | list item | 列表项目 |
| &lt;dl&gt; | definition list | 定义列表 |
| &lt;dt&gt; | definition term | 定义术语 |
| &lt;dd&gt; | definition description | 定义描述 |
| &lt;div&gt; | devision | 分区 |
| &lt;figure&gt; | figure | 独立单元 |
| &lt;figcaption&gt; | figure caption | 单元名称 |
| &lt;main&gt; | main | 主要内容 |
| &lt;pre&gt; | preformatted | 预格式 |

* **内容分区**

| 元素 | 描述 |
| :---: | :---: |
| &lt;address&gt; | &lt;address&gt;可以让作者为它最近的&lt;article&gt;或者&lt;body&gt;祖先元素提供联系信息。在后一种情况下，它应用于整个文档。 |
| &lt;article&gt; | &lt;article&gt;表示文档、页面、应用或网站中的独立结构，其意在成为可独立分配的或可复用的结构，如在发布中，它可能是论坛帖子、杂志或新闻文章、博客、用户提交的评论、交互式组件，或者其他独立的内容项目。 |
| &lt;aside&gt; | &lt;aside&gt;表示一个和其余页面内容几乎无关的部分，被认为是独立于该内容的一部分并且可以被单独的拆分出来而不会使整体受影响。其通常表现为侧边栏或者嵌入内容。他们通常包含在工具条，例如来自词汇表的定义。也可能有其他类型的信息，例如相关的广告、笔者的传记、web 应用程序、个人资料信息，或在博客上的相关链接。 |
| &lt;footer&gt; | &lt;footer&gt;表示最近一个章节内容或者根节点（sectioning root）元素的页脚。一个页脚通常包含该章节作者、版权数据或者与文档相关的链接等信息。 |
| &lt;header&gt; | &lt;header&gt;表示一组引导性的帮助，可能包含标题元素，也可以包含其他元素，像logo、分节头部、搜索表单等。 |
| &lt;h1&gt;~&lt;h6&gt; | 标题\(Heading\)元素拥有六个不同的级别，&lt;h1&gt;是最高级的，而&lt;h6&gt;则是最低的级别。一个标题元素能简要描述该节的主题。标题信息可以由用户代理可以使用，例如，自动构造某个文档中的内容表（就像本文档右边浮动栏一样）。 |
| &lt;hgroup&gt; | &lt;hgroup&gt;代表一个段的标题。它规定了在文档轮廓里（the outline of the document ）的单一标题是它所属的隐式或显式部分的标题。 |
| &lt;nav&gt; | &lt;nav&gt;描绘一个含有多个超链接的区域，这个区域包含转到其他页面，或者页面内部其他部分的链接列表。 |
| &lt;section&gt; | &lt;section&gt;表示文档中的一个区域（或节），比如，内容中的一个专题组，一般来说会有包含一个标题（heading）。一般通过是否包含一个标题 \(&lt;h1&gt;-&lt;h6&gt;\) 作为子节点 来辨识每一个&lt;section&gt;。 |

### CSS命名（id和class的命名）

更多的情况下推荐按照选择器命名的惯例进行设置，无论是 ID 还是 class，对任何东西最好总是根据它是什么而不是它看上去是什么样子来命名。



