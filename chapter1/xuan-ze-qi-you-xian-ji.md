#### 规则：

1、选择器越具体，优先级越高

2、同样优先级，写在后面的覆盖前面的

3、！important &gt;内联样式&gt; id &gt; class &gt;tag &gt;通配符



#### 选择器权重：

|  | 内联样式 | id选择器 | 类和伪类选择器 | 元素选择器 | 统配选择器 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 优先级 | 1000 | 100 | 10 | 1 | 0 |



#### 选择器继承：

```
可以的有 font-size font-family color  
```

```
不可以的有 border padding margin background-color width height等
```





