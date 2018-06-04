### 语意化标签

nav、aside、dialog、header、footer等语义化标签见'前端语义化'页。

### 新增事件属性

列举几个H5新增事件属性：

| onformchange | 当表单改变时运行脚本 |
| :--- | :--- |
| onforminput | 当表单获得用户输入时运行脚本 |
| oninput | 当元素获得用户输入时运行脚本 |

### Audio/Video

#### Video的基础使用

```
<video src="movie.ogg" width="320" height="240" controls="controls">
Your browser does not support the video tag.
</video>
```

#### Audio的基础使用

```
<audio src="song.ogg" controls="controls">
Your browser does not support the audio tag.
</audio>
```

### 地理定位

使用 `getCurrentPosition()`方法来获得用户的位置

### Web 存储

#### localStorage

##### 属性

localStorage 方法存储的数据没有时间限制

localStorage的使用遵循同源策略

每个域名容量5M

##### 用法

1. localStorage.setItem\("name", "张三"\);  在本地客户端存储一个字符串类型的数据
2. var data = localStorage.getItem\("name"\);  读取已存储在本地的数据
3. var data2 = localStorage.removeItem\("name"\); 从本地存储中移除键名为name的数据
4. localStorage.clear\(\) 移除本地存储所有数据

#### sessionStorage

##### 属性

sessionStorage 方法针对一个 session 进行数据存储。当用户关闭浏览器窗口后，数据会被删除。

##### 用法

sessionStorage的四个用法与localstorage一致。

#### Web 存储的使用优缺点

优点

* localStorage拓展了cookie的4K限制

缺点

* 浏览器的大小不统一，并且在IE8以上的IE版本才支持localStorage这个属性

* 所有的浏览器中都会把localStorage的值类型限定为string类型

* localStorage不能被爬虫抓取到

### Web workers

web worker 是运行在后台的 JavaScript，独立于其他脚本，不会影响页面的性能。您可以继续做任何愿意做的事情：点击、选取内容等等，而此时 web worker 在后台运行。用于更耗费 CPU 资源的任务。

#### 使用

1. 创建 web worker 文件,并使用_postMessage\(\)_方法向 HTML 页面传回一段消息。
2. 创建一个新的 web worker 对象，然后运行 "demo\_workers.js" 中的代码。

3. 向 web worker 添加一个 "onmessage" 事件监听器。

4. 如需终止 web worker，并释放浏览器/计算机资源，请使用 terminate\(\) 方法。

```
<!DOCTYPE html>
<html>
<body>

<p>Count numbers: <output id="result"></output></p>
<button onclick="startWorker()">Start Worker</button>
<button onclick="stopWorker()">Stop Worker</button>
<br /><br />

<script>
var w;

function startWorker()
{
if(typeof(Worker)!=="undefined")
{
  if(typeof(w)=="undefined")
    {
    w=new Worker("demo_workers.js");
    }
  w.onmessage = function (event) {
    document.getElementById("result").innerHTML=event.data;
  };
}
else
{
document.getElementById("result").innerHTML="Sorry, your browser
 does not support Web Workers...";
}
}

function stopWorker()
{
w.terminate();
}
</script>

</body>
</html>
```

### 应用缓存

如需启用应用程序缓存，请在文档的 &lt;html&gt;标签中包含 manifest 属性：

```
<!DOCTYPE HTML>
<html manifest="demo.appcache">
...
</html>
```

#### 组成

manifest 文件可分为三个部分：

* _CACHE MANIFEST_
  * 在此标题下列出的文件将在首次下载后进行缓存
* _NETWORK_
  * 在此标题下列出的文件需要与服务器的连接，且不会被缓存
* _FALLBACK_
  * 在此标题下列出的文件规定当页面无法访问时的回退页面（比如 404 页面）

#### 使用

CACHE MANIFEST是必需的

```
CACHE MANIFEST
/theme.css
/logo.gif
/main.js
```

上面的 manifest 文件列出了三个资源：一个 CSS 文件，一个 GIF 图像，以及一个 JavaScript 文件。当 manifest 文件加载后，浏览器会从网站的根目录下载这三个文件。然后，无论用户何时与因特网断开连接，这些资源依然是可用的。

NETWORK 小节规定哪些文件永远不会被缓存，且离线时是不可用的，可以使用星号来指示所有其他资源/文件都需要因特网连接。

FALLBACK 小节规定如果无法建立因特网连接，则用 某文件 替代 /html5/ 目录中的所有文件

#### 属性

一旦应用被缓存，它就会保持缓存直到发生下列情况：

* 用户清空浏览器缓存
* manifest 文件被修改（参阅下面的提示）
* 由程序来更新应用缓存

### Web Socket

#### 意义

HTTP 协议有一个缺陷：通信只能由客户端发起 ，websocket可以实现服务端主动推送。

#### 属性

（1）建立在 TCP 协议之上，服务器端的实现比较容易。

（2）与 HTTP 协议有着良好的兼容性。默认端口也是80和443，并且握手阶段采用 HTTP 协议，因此握手时不容易屏蔽，能通过各种 HTTP 代理服务器。

（3）数据格式比较轻量，性能开销小，通信高效。

（4）可以发送文本，也可以发送二进制数据。

（5）没有同源限制，客户端可以与任意服务器通信。

（6）协议标识符是`ws`（如果加密，则为`wss`），服务器网址就是 URL。

#### 用法

```
//客户端与服务器进行连接
var ws = new WebSocket("wss://echo.websocket.org");
//指定连接成功后的回调函数
ws.onopen = function(evt) { 
  console.log("Connection open ..."); 
  ws.send("Hello WebSockets!");
};
//指定收到服务器数据后的回调函数
ws.onmessage = function(evt) {
  console.log( "Received Message: " + evt.data);
  ws.close();
};
//指定连接关闭后的回调函数
ws.onclose = function(evt) {
  console.log("Connection closed.");
};    
```

#### 缺点

对前端开发者，往往要具备数据驱动使用javascript的能力，且需要维持住ws连接（否则消息无法推送）；对后端开发者而言，难度增大了很多，一是长连接需要后端处理业务的代码更稳定（不要随便把进程和框架都crash掉），二是推送消息相对复杂一些，三是成熟的http生态下有大量的组件可以复用，websocket则太新了一点。

### 表单

#### 新增表单类型

* email
* url

* number
* range
* Date pickers \(date, month, week, time, datetime, datetime-local\)
* search
* color

#### 新的表单元素

datalist规定输入域的选项列表。

```
<form action="/example/html5/demo_form.asp" method="get">
Webpage: <input type="url" list="url_list" name="link" />
<datalist id="url_list">
	<option label="W3School" value="http://www.w3school.com.cn" />
	<option label="Google" value="http://www.google.com" />
	<option label="Microsoft" value="http://www.microsoft.com" />
</datalist>
<input type="submit" />
</form>
```

### Canvas

见'Canvas'页。

