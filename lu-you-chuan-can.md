### 路由传参

点击不同的li进行不同跳转并传参

```
<li v-for="article in articles" @click="getDescribe(article.id)">
```

#### 方法一 通过动态路由的：值传参

    getDescribe(id) {
    //   直接调用$router.push 实现携带参数的跳转
         this.$router.push({
        path: `/describe/${id}`,
    	})
    }
    //路由配置
    {
         path: '/describe/:id',
         name: 'Describe',
         component: Describe
    }
    //取参数
    $route.params.id

#### 方法二 通过name确定路由，通过params来传递参数

```
this.$router.push({
          name: 'Describe',
          params: {
            id: id
          }
})
//路由配置
{
     path: '/describe',
     name: 'Describe',
     component: Describe
}
//取参数
$route.params.id
```

#### 方法三 使用query

```
this.$router.push({
          path: '/describe',
          query: {
            id: id
          }
})
//路由配置
{
     path: '/describe',
     name: 'Describe',
     component: Describe
}
//取参数
$route.query.id
```

  


