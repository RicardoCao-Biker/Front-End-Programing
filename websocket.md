#### 意义

HTTP 协议有一个缺陷：通信只能由客户端发起 ，websocket可以实现服务端主动推送。

#### 属性

（1）建立在 TCP 协议之上，服务器端的实现比较容易。（2）与 HTTP 协议有着良好的兼容性。默认端口也是80和443，并且握手阶段采用 HTTP 协议，因此握手时不容易屏蔽，能通过各种 HTTP 代理服务器。（3）数据格式比较轻量，性能开销小，通信高效。（4）可以发送文本，也可以发送二进制数据。（5）没有同源限制，客户端可以与任意服务器通信。（6）协议标识符是`ws`（如果加密，则为`wss`），服务器网址就是 URL。

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

