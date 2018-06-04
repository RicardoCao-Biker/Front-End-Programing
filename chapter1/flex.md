#### flex-direction属性

主轴的方向

* `row`（默认值）：主轴为水平方向，起点在左端。

* `row-reverse`：主轴为水平方向，起点在右端。

* `column`：主轴为垂直方向，起点在上沿。

* `column-reverse`：主轴为垂直方向，起点在下沿。

#### justify-content属性

项目在主轴上的对齐方式

* `flex-start`（默认值）：左对齐

* `flex-end`：右对齐

* `center`： 居中

* `space-between`：两端对齐，项目之间的间隔都相等。

* `space-around`：每个项目两侧的间隔相等。所以，项目之间的间隔比项目与边框的间隔大一倍。

#### align-items属性

交叉轴上如何对齐

* `flex-start`：交叉轴的起点对齐。

* `flex-end`：交叉轴的终点对齐。

* `center`：交叉轴的中点对齐。

* `baseline`: 项目的第一行文字的基线对齐。

* `stretch`（默认值）：如果项目未设置高度或设为auto，将占满整个容器的高度。

#### flex属性

`flex`属性默认值为`0 1 auto`

`flex:flex-grow,flex-shrink,flex-basis`

* `flex-grow`属性定义项目的放大比例，默认为`0`，即如果存在剩余空间，也不放大。 如果所有项目的`flex-grow`属性都为1，则它们将等分剩余空间（如果有的话）

* `flex-shrink`属性定义了项目的缩小比例，默认为1，即如果空间不足，该项目将缩小。

* `flex-basis`属性定义了在分配多余空间之前，项目占据的主轴空间（main size）。浏览器根据这个属性，计算主轴是否有多余空间。它的默认值为`auto`，即项目的本来大小。

**另外：下面两个表达式相等：**

```
.item {flex: 1;}
.item {
  flex-grow: 1;
  flex-shrink: 1;
  flex-basis: 0%;
}
```



