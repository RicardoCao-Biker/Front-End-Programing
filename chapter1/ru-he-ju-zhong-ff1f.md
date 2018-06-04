#### 水平居中

1. 子元素margin:0 auto,子元素要有宽度

2. 父元素text-align:center,子元素inline-block

3. 父元素position:relative,子元素position:absolute;left:50%;transform:translateX\(-50%\)

4. 父元素display:flex;justify-content:center;\(需要子元素有宽度\)

5. 父元素display:tablecell;text-align:center

#### 垂直居中

1. display:inline-block;vertical-align:middle

2. 父元素position:relative,子元素position:absolute;top:50%;transform:translateY\(-50%\)

3. line-height:200px

4. 父元素display:tablecell;vertical-align:center

5. 父元素display:flex;align-items:center\(需要子元素有宽度\)

#### 水平垂直居中

1.

```
父{position:relative}
子{
  position:absolute;
  top:0,left:0;right:0,bottom:0;
  margin:auto;}
```

2.

```
父{
display:flex;
content-justify:center;
align-items:center;}
```

3.

```
父{position：relative}
子{
position:absolute;
left:50%;
top:50%
transform:translate(-50%,-50%)}
```



