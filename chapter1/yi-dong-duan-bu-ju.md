#### 响应式

利用@media进行断点，在每个断点中编写css

```
@media (max-width:1000px){
  div{background:blue;}
}
@media (min-width:1000px) and (max-width:1150px){
  div{background: yellow;}
}
@media only screen and (max-width:1150px){
  div{border:solid 1px;}
}
```

优点：兼容性好，@media在ie9以上是支持的，PC和MOBILE是同一套代码的，不用分开。

缺点：要写得css相对另外两个多很多，而且各个断点都要做好。css样式会稍微大点，更麻烦。

#### REM

REM这个单位，会根据html的`font-size`大小进行转换

为了方便计算，时常将在`<html>`元素中设置`font-size`值为`62.5%`:[·](http://caibaojian.com/rem-and-px.html)

相当于在`<html>`中设置`font-size`为`10px`

```
html{font-size:62.5%;} //10px
p{padding-top:1rem;} 
```

* 通过屏幕宽度计算html的字体大小\(假设设计稿为750px\)

```
(function (doc, win) {
  var docEl = doc.documentElement,
  resizeEvt = 'orientationchange' in window ? 'orientationchange' : 'resize',
  recalc = function () {
  var clientWidth = docEl.clientWidth;
  if (!clientWidth) return;
  docEl.style.fontSize = 100 * (clientWidth / 750) + 'px';
  };
  if (!doc.addEventListener) return;
 win.addEventListener(resizeEvt, recalc, false);
 doc.addEventListener('DOMContentLoaded', recalc, false);
})(document, window);
```

优点：能维持能整体的布局效果，移动端兼容性好，不用写多个css代码，而且还可以利用@media进行优化。

缺点：开头要引入一段js代码，单位都要改成rem\(font-size可以用px\)，计算rem比较麻烦\(可以引用预处理器，但是增加了编译过程，相对麻烦了点\)。pc和mobile要分开。

#### 设置viewport中的width

* 这种方案，就是定死viewport中的width大小。

* 比如设计稿是750的，然后就在代码上写：

  ```
  <meta name='viewport' content='width=750' />
  ```

优点：和REM相同，而且不用写rem，直接使用px，更加快捷。

缺点：效果可能没rem的好，图片可能会相对模糊，而且无法使用@media进行断点，不同size的手机上显示，高度间距可能会相差很大。

