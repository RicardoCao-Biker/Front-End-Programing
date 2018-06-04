#### 选择器\(包括伪元素、伪类等\)

![](http://img2.sycdn.imooc.com/5acf028c000157b904760870.jpg)

![](http://img3.sycdn.imooc.com/5acf028c0001f1a204770340.jpg)

#### 边框\(border-image、border-radius、box-shadow\)

* border-radius
* box-shadow

```
div{
box-shadow: 10px 10px 5px #888888;}
```

* border-image

```
div{
border-image:url(border.png) 30 30 round;}
```

* text-shadow

```
h1{
text-shadow: 5px 5px 5px #FF0000;}
```

#### 字体\(@font-face\)

```
<style> 
     @font-face{
     font-family: myFirstFont;
     src: url('Sansation_Light.ttf')}

     div{
     font-family:myFirstFont}
</style>
```

#### 转换、形变\(transform\)

transform的主要2D转换方法

| translate\(x,y\) | 定义 2D 转换，沿着 X 和 Y 轴移动元素。 |
| :--- | :--- |
| translateX\(n\) | 定义 2D 转换，沿着 X 轴移动元素。 |
| translateY\(n\) | 定义 2D 转换，沿着 Y 轴移动元素。 |
| scale\(x,y\) | 定义 2D 缩放转换，改变元素的宽度和高度。 |
| scaleX\(n\) | 定义 2D 缩放转换，改变元素的宽度。 |
| scaleY\(n\) | 定义 2D 缩放转换，改变元素的高度。 |
| rotate\(angle\) | 定义 2D 旋转，在参数中规定角度。 |

#### 过渡\(transition\)

```
transition: property duration timing-function delay;
```

| 值 | 描述 |
| :--- | :--- |
| [transition-property](http://www.w3school.com.cn/cssref/pr_transition-property.asp) | 规定设置过渡效果的 CSS 属性的名称。 |
| [transition-duration](http://www.w3school.com.cn/cssref/pr_transition-duration.asp) | 规定完成过渡效果需要多少秒或毫秒。 |
| [transition-timing-function](http://www.w3school.com.cn/cssref/pr_transition-timing-function.asp) | 规定速度效果的速度曲线。 |
| [transition-delay](http://www.w3school.com.cn/cssref/pr_transition-delay.asp) | 定义过渡效果何时开始 |

#### 动画\(animation\)

```
animation: name duration timing-function delay iteration-count direction;
```

| 值 | 描述 |
| :--- | :--- |
| _animation-name_ | 规定需要绑定到选择器的 keyframe 名称。。 |
| _animation-duration_ | 规定完成动画所花费的时间，以秒或毫秒计。 |
| _animation-timing-function_ | 规定动画的速度曲线。 |
| _animation-delay_ | 规定在动画开始之前的延迟。 |
| _animation-iteration-count_ | 规定动画应该播放的次数。 |
| _animation-direction_ | 规定是否应该轮流反向播放动画。 |



