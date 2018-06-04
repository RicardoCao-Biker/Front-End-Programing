#### 1、浮动带来的副作用：

1）块状元素，会钻进浮动元素的下面，被浮动元素所覆盖

![](https://img-blog.csdn.net/20170510174458144?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvYmFpZHVfMzcxMDcwMjI=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

2）行内元素，例如文字， 则会环绕在浮动元素的周围，为浮动元素留出空间

![](https://img-blog.csdn.net/20170510174554114?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvYmFpZHVfMzcxMDcwMjI=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

3）浮动元素的父元素坍缩

![](https://img-blog.csdn.net/20170510174611546?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvYmFpZHVfMzcxMDcwMjI=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

#### 2、清除浮动：

![](https://img-blog.csdn.net/20170510175815652?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvYmFpZHVfMzcxMDcwMjI=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

```
.clearfix:after{
 content:"."; 
 display:block; 
 height:0; 
 clear:both; 
 visibility:hidden; 
}
//为兼容IE6,IE7，因为ie6,ie7不能用after伪类。加上下面代码
.clearfix{zoom:1}
```



