#### String 对象方法

**length 字符串的长度**

**charAt\(\) 返回在指定位置的字符。**

**concat\(\) 连接字符串。**

**indexOf\(\) 检索字符串。**

**lastIndexOf\(\) 从后向前搜索字符串。**

**match\(\) 找到一个或多个正则表达式的匹配。**

**replace\(\) 替换与正则表达式匹配的子串。**

**search\(\) 检索与正则表达式相匹配的值。**

**slice\(\)  提取字符串的片断，并在新的字符串中返回被提取的部分。**

```
var str="Hello happy world!"
document.write(str.slice(6,11)) //happy
```

**split\(\) 把字符串分割为字符串数组。**

**substring\(\) 提取字符串中两个指定的索引号之间的字符。**

```
var str="Hello world!"
document.write(str.substring(3,7))// lo w
```

**toLowerCase\(\) 把字符串转换为小写。**

**toUpperCase\(\) 把字符串转换为大写。**

**toString\(\) 返回字符串。**



* str.charAt\(\)和str\[\]的区别

```
var s = "abc";
s[1];        // b
s.charAt(1); // b
s[5];        // undefined
s.charAt(5); // ""
```



