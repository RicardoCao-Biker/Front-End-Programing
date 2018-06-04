#### 特性

* BFC元素里面的元素不会在布局上影响外侧的元素,

* 计算BFC的高度时，浮动元素也参与计算

* 内部的Box会在垂直方向，一个接一个地放置

* BFC的区域不会与float box重叠。

#### 作用

1. 同一个 BFC 下外边距会发生折叠

2. BFC 可以包含浮动的元素\(清除浮动\)

3. BFC 可以阻止元素被浮动元素覆盖

* overflow：hidden 清除浮动

* overflow：hidden 取消父子margin合并（子设置margin，父也会有margin）

  > 因为BFC内部的元素和外部的元素绝对不会互相影响，因此， 当BFC外部存在浮动时，它不应该影响BFC内部Box的布局，BFC会通过变窄，而不与浮动有重叠。同样的，当BFC内部有浮动时，为了不影响外部元素的布局，BFC计算高度时会包括浮动的高度。避免margin重叠也是这样的一个道理。

#### 如何触发BFC

1. 根元素

2. float属性不为none

3. position为absolute或fixed

4. display为inline-block, table-cell, table-caption, flex, inline-flex

5. overflow不为visible\( hidden,scroll,auto, \)



