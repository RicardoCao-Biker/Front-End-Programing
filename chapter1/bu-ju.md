### 左侧固定右侧自适应

```
 left{
  width:100xp;
  float:left
 }
 right{margin-left:100px}
```

```
 left{
  position:absolute;
  left:0;
  width:100px}
 right{
  position:absolute;
  left:100px;
  width:calc(100% - 100px)}
```

```
  parent{display:flex}
  left{flex:0 0 100px}
  right{flex:1}
```

### 两边固定中间自适应的三列布局

#### 利用flex

```
  .father {
    display: flex;
    }
  .left,
  .right {
    flex: 0 1 100px;
  }
  .middle {
    flex: 1;
  }
```

#### 双飞翼布局\(两边定宽，中间自适应\)

```
<div class="box">
  <div class="middle-wrap">
    <div class="middle"></div>
  </div>
  <div class="left"></div>
  <div class="right"></div>
</div>

.box {
    position: relative;
    height: 100px;
  }
  .middle-wrap {
    position: relative;
    float: left;
    width: 100%;
    height: 100%;
  }
  .middle-wrap .middle {
    height: 100%;
    margin: 0 100px; /*留出距离*/
    background-color: yellow;
  }
  .left {
    float: left;
    width: 100px;
    margin-left: -100%;
    height: 100%;
    background-color: red;
  }
  .right {
    float: left;
    width: 100px;
    height: 100%;
    margin-left: -100px;
    background-color: green;
  }

```



