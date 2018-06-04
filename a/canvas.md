#### 区别

canvas为标量图，svg为矢量图，canvas为html5新增。

#### canvas的使用

* HTML

`<canvas id="canvas" height="200" width="350"></canvas>`

* JS

```
let canvas=document.getElementById("canvas");
let ctx = canvas.getContext('2d');
//绘制表框
function drawBackground() {
  ctx.save();
  ctx.translate(r, r);
  ctx.beginPath();//起始一条路径，或重置当前路径
  ctx.lineWidth = 10 * rem; //以0，0为原点，r为半径，0为起始角，2*Math.PI为结束角，顺时针画圆
  ctx.arc(0, 0, r - ctx.lineWidth / 2, 0, 2 * Math.PI, false); //画圆
  ctx.stroke();//绘制已定义的路径
}
//绘制秒针
function drawSecond(second) {
  ctx.save();
  ctx.beginPath();
  ctx.fillStyle = '#c14443';
  ctx.rotate(2 * Math.PI / 60 * second);//旋转
  ctx.moveTo(-2, 20 * rem);
  ctx.lineTo(2, 20 * rem);
  ctx.lineTo(1, -r + 18 * rem);
  ctx.lineTo(-1, -r + 18 * rem);
  ctx.fill();
  ctx.restore();
  ctx.drawImage(img,10,10);//向画布上绘制图像、画布或视频
  }
function draw() {
  ctx.clearRect(0, 0, width, height);//清除前一帧画面
  var now = new Date();//获取此刻时间
  var seconds = now.getSeconds();
  drawBackground();
  drawSecond(seconds);
  }
setInterval(draw, 1000);
```

#### Canvas问题:高清屏幕下图片模糊

不管当前的`devicePixelRatio`的值是多少，统一将`canvas`DOM节点的width属性设置为其`css`width属性的两倍，同理将height属性也设置为`css`height属性的两倍，即：

`<canvas width="320" height="180" style="width:160px;height:90px;"></canvas>`

这样整个 canvas 的坐标系范围就扩大为两倍，但是在浏览器的显示大小没有变，canvas画图的时候，按照扩大化的坐系来显示，不清晰的问题就得以改善了

### SVG实例

```
<!DOCTYPE html>
<html>
<body>

<svg xmlns="http://www.w3.org/2000/svg" version="1.1" height="190">
   <polygon points="100,10 40,180 190,60 10,60 160,180"
   style="fill:red;stroke:blue;stroke-width:3;fill-rule:evenodd;" />
</svg>
 
</body>
</html>
```



