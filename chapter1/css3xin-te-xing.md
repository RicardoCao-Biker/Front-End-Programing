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

#### 动画\(animation\)

#### 弹性盒模型\(flex-box\)

#### 媒体查询\(@media\)，监听屏幕尺寸的变化



