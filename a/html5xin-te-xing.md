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

1.  localStorage.setItem\("name", "张三"\);  在本地客户端存储一个字符串类型的数据
2.  var data = localStorage.getItem\("name"\);  读取已存储在本地的数据
3.  var data2 = localStorage.removeItem\("name"\); 从本地存储中移除键名为name的数据
4.  localStorage.clear\(\) 移除本地存储所有数据

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
  - 在此标题下列出的文件将在首次下载后进行缓存
* _NETWORK_
  - 在此标题下列出的文件需要与服务器的连接，且不会被缓存
* _FALLBACK_
  - 在此标题下列出的文件规定当页面无法访问时的回退页面（比如 404 页面）

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

### 表单



### Canvas

见'Canvas'页。



