**GET用来读数据，POST用来写数据**

1. 安全：**GET没有POST安全**

2. **GET的参数有长度限制**，一般是1024个字符，POST的参数没有长度限制，一般是4-10Mb

3. 包：GET请求只需发一个包，POST请求需要发两个以上包（因为POST有消息体）

4. GET的参数放在URL的查询参数里，POST的参数放在请求消息体（数据）里

   * **GET 请求可被缓存**

   * GET 请求保留在浏览器历史记录中

   * GET 请求可被收藏为书签

   * GET 请求不应在处理敏感数据时使用

   * GET 请求有长度限制

   * GET 请求只应当用于取回数据

   * **POST 请求不会被缓存**

   * POST 请求不会保留在浏览器历史记录中

   * POST 不能被收藏为书签

   * POST 请求对数据长度没有要求



