### 属性

参考链接 [https://deerchao.net/tutorials/regex/regex.htm](https://deerchao.net/tutorials/regex/regex.htm)

### 使用

* 邮箱

`/^([a-z0-9_\.-]+)@([0-9a-z\.-]+)\.([a-z]{2,6})$/`

* 密码 6-16位数字和字母的组合

`/^[a-z0-9_-]{6,16}$/`

* 手机号

`if(!(/^1[34578][0-9]{9}$/.test(phone)))`

* 千位分隔

```
var str = '1234657';
str.replace(/\B(?=(\d{3})+$)/g,',')
"1,234,657"
```

* 让2013-6-7 变成 2013.6.7

```
let str = '2013-6-7';
let regExp = /-/g;
console.log(str.replace(regExp, '.')); //2013-6-7
```

* 从一个字符串中提取链接地址

```
let str = 'IT面试题博客中包含很多  <a href="http://hi.baidu.com/mianshiti/blog/category/微软面试题">微软面试题</a>';
let regExp = /<a(?: [^>]*)+href="(.*)"(?: [^>]*)*>/;
console.log(regExp.exec(str)[1]);
```

* 给定这样一个连字符串，写一个function转换为驼峰命名法形式的字符串

```
var s1 = "get-element-by-id";
function camelCased(str) {
  let regExp = /-(\w)/g;
  str.replace(regExp, function(match, p) {
      return p.toUpperCase();
   })
}
camelCased(s1);
```

* 判断是否以元音字母结尾

```
let str1= 'animal';
let str2 = 'li';
let str3 = 'foO';
let regExp = /[a,e,i,o,u]$/i;
console.log(regExp.test(str1)); //false
console.log(regExp.test(str2)); //true
console.log(regExp.test(str3)); //true
```

* 给定字符串 str，检查其是否包含 3 个连续的数字,如果包含，返回最新出现的 3 个数字的字符串,如果不包含，返回 false

```
let str1 = 'abc123efg';
function captureThreeNumbers(str) {
    let res;
    if (res = str.match(/\d{3}/)) {
        return res[0];
    } else {
        return false;
    }
}
console.log(captureThreeNumbers(str1)); //123
```

* 给定字符串 str，检查其是否符合如下格式 XXX-XXX-XXXX,其中 X 为 Number 类型

```
let regExp =  /^(\d{3}-){2}\d{4}$/;
console.log(regExp.test('123-456-7890'));
```

* 将单词is替换为IS

```
let str = 'English poetry is one of their great heritages';
console.log(str.replace(/\bis\b/,'IS'));
```



