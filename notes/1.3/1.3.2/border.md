## border属性
+ border属性需要三要素：线宽度、线型、线颜色
```
border: 1px solid red;
```
+ 线型

    线型值|意义
    -|-
    solid|实线
    dashed|虚线
    dotted|点状线

+ 边框三要素可以拆分为小属性

    小属性|意义
    -|-
    border-width|线宽
    border-style|线型
    border-color|线颜色


##### 四个方向的边框

属性|意义
-|-
border-top|上边框
border-right|右边框
border-bottom|下边框
border-left|左边框

+ 四个方向边框的三要素小属性

    属性|意义
    -|-
    border-top-width|上边框宽度
    border-top-style|上边框线型
    border-top-color|上边框颜色
    boreder-rigth-width|右边框宽度
    boreder-rigth-style|右边框线型
    boreder-rigth-color|右边框颜色
    boreder-bottom-width|下边框宽度
    boreder-bottom-style|下边框线型
    boreder-bottom-color|下边框颜色
    boreder-left-width|左边框宽度
    boreder-left-style|左边框线型
    boreder-left-color|左边框颜色


##### 去掉边框
+ border:none;属性即可去掉边框
+ border-left:none;去掉左边框

##### 利用边框制作三角形
```
width:0;
height:0;
/*transparent是透明色*/
border:20px solid transparent;
border-top-color:red;
```

## 圆角
+ border-radius属性的值通常为px单位，表示圆角的半径
```
border-radius:10px;
```
+ 单独设置四个圆角
```
border-radius:10px 20px 30px 40px;
/*左上 右上 左下 右下*/
```
+ 小属性

    属性|意义
    -|-
    border-top-left-radius|左上角
    border-top-right-radius|右上角
    border-bottom-left-radius|左下角
    border-bottom-right-radius|右下角


+ 百分比单位
    + border-radius属性的值也可以用百分比做单位，表示圆角起始于每条边的哪里
    ```
    border-radius:50%
    ```

## 盒子阴影
+ box-shadow属性
```
box-shadow:10px 20px 30px rgba(0,0,0,.4);
/* x偏移 y偏移 模糊量 颜色*/
```
+ 阴影延展
```
box-shadow:10px 20px 30px 40px rgba(0,0,0,.4);
/* x偏移 y偏移 模糊量 阴影延展 颜色*/
```
+ 内阴影
```
box-shadow: inset 10px 20px 30px 40px rgba(0,0,0,.4);
/*内阴影 x偏移 y偏移 模糊量 阴影延展 颜色*/
```
+ 多阴影，box-shadow属性值可以用逗号隔开多个，表示携带多个阴影