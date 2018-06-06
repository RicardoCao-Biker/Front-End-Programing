| _特性_ | _Cookie_ | _Localstorage_ | _sessionstorage_ |
| :--- | :--- | :--- | :--- |
| 生命周期 | 一般由服务器生成，可设置失效时间。如果在浏览器端生成Cookie，默认是关闭浏览器后失效。 | 除非被清除，否则永久保存 | 仅在当前会话下有效，关闭页面或浏览器后被清除 |
| 数据大小 | 4k | 5MB |  |
| 与服务器端通信 | 每次都会携带在HTTP头中，如果使用cookie保存过多数据会带来性能问题 | 仅在客户端\(即浏览器\)中保存，不参与和服务器的通信 |  |
| 用途 | 用于标识用户身份 | 用于浏览器端缓存数据 |  |
| 易用性 | cookie需要自己封装setCookie，getCookie | 可以用源生接口，也可再次封装来对Object和Array有更好的支持 |  |

#### cookie

* HTTP响应通过Set-cookie设置Cookie

* 浏览器访问指定域名时必须带上cookie作为request header

* cookie一般用来记录用户信息

#### session

* session是服务器端的内存

* session一般通过在cookie里记录sessionID实现

* sessionID一般是随机数

#### localstorage和cookie区别

* cookie会随请求发送到服务器上，localstorage不会

* cookie一般大小4k，localstorage一般是5M



