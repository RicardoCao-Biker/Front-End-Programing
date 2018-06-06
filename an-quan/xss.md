### 什么是XSS攻击（跨域脚本攻击 ），如何预防？\(\*\)

* 发生了不在预期内执行的JS代码 ,达到获取本地的部分cookie信息等目的 。例如：网站form表单收集数据的时候，有的用户非法/恶意的把”html/css/js”代码内容给植入到form表单域中

#### XSS的分类

**存储型XSS、反射型XSS、DOM-XSS**

#### 1、存储型XSS

数据库中存有的存在XSS攻击的数据，返回给客户端。若数据未经过任何转义。被浏览器渲染。就可能导致XSS攻击；

#### 2、反射型XSS

将用户输入的存在XSS攻击的数据，发送给后台，后台并未对数据进行存储，也未经过任何过滤，直接返回给客户端。被浏览器渲染。就可能导致XSS攻击；

#### 3、DOM-XSS

纯粹发生在客户端的XSS攻击

#### 预防：从输入到输出都需要过滤、转义。

> **输入**
>
> 1. 在产品形态上，针对不同输入类型，对输入做变量类型限制。 如，`http://xss.qq.com?default=12`，Default值强制限制为整形。
>
> 2. 字符串类型的数据，需要针对&lt;、&gt;、/、’、”、&五个字符进行实体化转义。
>
> ![](http://mmbiz.qpic.cn/mmbiz_png/kn3fIZB16MoQzibiavf1PWI4cCd9p4nJs2Fe1olQHQd2icPPHicmm4AVfLSRxJLnicTXUiamHA4gBvejVhmUiaNPwsGIQ/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1)
>
> ```
> function(a){
>         return a.replace(/&/g, "&amp;").replace(/</g, "&lt;").replace(/>/g, "&gt;").replace(/"/g, "&quot;").replace(/'/g, "&apos;");
>     }
> ```
>
> **输出**
>
> 即使在客户端对用户的输入做了过滤、转义，攻击者一样可能，通过截包，转发等手段，修改你的请求包体。最终还是要在数据输出的时候做数据转义。
>
> 1. 如果是字符串操作，保证字符串被引号包裹。
>
> 2. 输出到页面上的数据必须使用相应方法转义，前端可以考虑寻找js插件处理。目前jquery-encoder，可用于前端json转义。使用方式与ESAPI类似，在需要渲染的时候进行转义。



* 预防主要通过对输入数据的对每个用户的输入都做严格检查

* 在输出的时候，对某些特殊字符进行转义，替换等 再过滤掉危险标签、属性和事件等。

* 表单输入的字符进行实体转码，把&lt;替换成&lt，&gt;替换成&gt ，&替换成&amp

* 为Cookie加上HttpOnly标记，以避免cookie劫持的危险。

* 不要用innerHTML,用innerText



