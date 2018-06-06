### 同源策略

#### 意义

同源策略主要用来防止CSRF攻击

1. 用户登录了自己的银行页面[http://mybank.com](https://link.zhihu.com/?target=http%3A//mybank.com)，[http://mybank.com](https://link.zhihu.com/?target=http%3A//mybank.com)向用户的cookie中添加用户标识。

2. 用户浏览了恶意页面[http://evil.com](https://link.zhihu.com/?target=http%3A//evil.com)。执行了页面中的恶意AJAX请求代码。

3. [http://evil.com](https://link.zhihu.com/?target=http%3A//evil.com)向[http://mybank.com](https://link.zhihu.com/?target=http%3A//mybank.com)发起AJAX HTTP请求，请求会默认把[http://mybank.com](https://link.zhihu.com/?target=http%3A//mybank.com)对应cookie也同时发送过去。

4. 银行页面从发送的cookie中提取用户标识，验证用户无误，response中返回请求数据。此时数据就泄露了。而且由于Ajax在后台执行，用户无法感知这一过程。

#### 属性

如果非同源，共有三种行为受到限制。

> （1） Cookie、LocalStorage 和 IndexDB 无法读取。
>
> （2） DOM 无法获得。
>
> （3） AJAX 请求不能发送。

### 跨域

* js里发送ajax请求，如果请求的URL和当前的URL非同域，浏览器拒接提供接受的收据并报错。

* 解决办法：JSONP、CORS、代理服务器、POSTMESSAGE（主用于：页面和其打开的新窗口的数据传递）

* 相比JSONP只能发`GET`请求，CORS允许任何类型的请求。

#### 代理服务器

例如[www.123.com/index.html](www.123.com/index.html)需要调用[www.456.com/server.php](www.456.com/server.php)，可以写一个接口[www.123.com/server.php](www.123.com/server.php)，由这个接口在后端去调用[www.456.com/server.php](www.456.com/server.php)并拿到返回值，然后再返回给index.html，这就是一个代理的模式。相当于绕过了浏览器端，自然就不存在跨域问题。

#### JSONP

##### 实现

它的基本思想是，网页通过添加一个`<script>`元素，向服务器请求JSON数据，这种做法不受同源政策限制；服务器收到请求后，将数据放在一个指定名字的回调函数里传回来。

```
function addScriptTag(src) {
  var script = document.createElement('script');
  script.setAttribute("type","text/javascript");
  script.src = src;
  document.body.appendChild(script);
}

window.onload = function () {
  addScriptTag('http://example.com/ip?callback=foo');
}

function foo(data) {
  console.log('Your public IP address is: ' + data.ip);
};
//服务器返回
foo({
  "ip": "8.8.8.8"
});
```

##### 缺点

JSONP只能发GET请求

#### CORS（\*）

##### 意义

允许浏览器向跨源服务器，发出[`XMLHttpRequest`](http://www.ruanyifeng.com/blog/2012/09/xmlhttprequest_level_2.html)请求，从而克服了AJAX只能同源使用的限制

##### 性质

* 浏览器将CORS请求分成两类：简单请求（simple request）和非简单请求（not-so-simple request）。

* 简单请求请求方法是以下三种方法之一：HEAD/GET/POST

* 整个CORS通信过程，都是浏览器自动完成，不需要用户参与。对于开发者来说，CORS通信与同源的AJAX通信没有差别，代码完全一样。浏览器一旦发现AJAX请求跨源，就会自动添加一些附加的头信息。

##### 使用

在头信息之中，增加一个`Origin`字段 ,用来说明本次请求来自哪个源（协议 + 域名 + 端口）。服务器根据这个值，决定是否同意这次请求 .

如果`Origin`指定的源，不在许可范围内，服务器会返回一个正常的HTTP回应。浏览器发现，这个回应的头信息没有包含`Access-Control-Allow-Origin`字段（详见下文），就知道出错了，从而抛出一个错误，被`XMLHttpRequest`的`onerror`回调函数捕获。注意，这种错误无法通过状态码识别，因为HTTP回应的状态码有可能是200。

如果`Origin`指定的域名在许可范围内，服务器返回的响应,会多出几个头信息字段。

```
//该字段是必须的。它的值要么是请求时Origin字段的值，要么是一个*，表示接受任意域名的请求
Access-Control-Allow-Origin: http://api.bob.com
//该字段可选。表示是否允许发送Cookie。
Access-Control-Allow-Credentials: true
Access-Control-Expose-Headers: FooBar
Content-Type: text/html; charset=utf-8
```

如果指定要发cookie，另一方面，开发者必须在AJAX请求中打开`withCredentials`属性。 否则，即使服务器同意发送Cookie，浏览器也不会发送。

```
var xhr = new XMLHttpRequest();
xhr.withCredentials = true;
```

##### 缺点

* 需要控制好允许访问的域名

* 浏览器兼容性稍弱



