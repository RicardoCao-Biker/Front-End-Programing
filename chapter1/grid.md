参考文档链接：[http://topic.42du.cn/grid](http://topic.42du.cn/grid)

### 重点属性

#### 网格容器

将属性`display`值设为`grid`或`inline-grid`就创建了一个网格容器，所有容器直接子结点自动成为网格项目。

* display: grid网格项目按行排列，网格项目占用整个容器的宽度。

* display: inline-grid网格项目按行排列，网格项目宽度由自身宽度决定。

#### 显示网格

属性`grid-template-rows`和`grid-template-columns`用于显示定义网格，分别用于定义行轨道和列轨道。

* 属性`grid-template-rows:50px 100px`用于定义行的尺寸。

* 属性`grid-template-columns:50px 100px`用于定义列的尺寸。

* 长度值可以是`auto`，表示轨道尺寸可以根据内容大小进行伸长或收缩。

#### 用网格线编号定位项目

* 通过设置网格线编号直接定位单个子元素

```
grid-row-start:    2;
grid-row-end:      3;
grid-column-start: 2;
grid-column-end:   3;
```

* 属性`grid-column`是`grid-column-start`和`grid-column-end`的简写形式。

```
grid-column: 3 / 4; 
//二者等价
grid-column-start:3;
grid-column-end:4;
```

* 通过`grid-column-start`和`grid-column-end`属性值的设置，使该网格项目跨越多列。行同理。

#### 网格项目的对齐方式

* 属性`justify-items`以行轴为参照对齐项目\(水平\)，属性`align-items`以列轴为参照对齐项目\(垂直\)。



