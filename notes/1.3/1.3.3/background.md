## background-color属性
+ background-color属性表示背景颜色
+ 背景颜色可以用十六进制、rgb()、rgba()表示法表示
+ padding区域是有背景颜色的

## background-image属性
+ background-image属性用来设置背景图片，图片路径要写到url()圆括号中，可以是相对路径，也可以是http:// 开头的绝对路径
```
background-image: url(images/bg1.jpg);
```
+ 如果样式表是外链的，那么要书写从CSS出发
到图片路径，而不是从html出发

## background-repeat属性
+ background-repeat属性用来设置背景的重复模式

值|意义
-|-
repeat;|x、y均不平铺
repeat-x;|x平铺
repeat-y;|y平铺
no-repeat;|不平铺

## background-sixe属性
+ background-sixe属性用来设置背景图片的尺寸，兼容到IE9
```
background-size: 100px 200px;
/*宽度  高度*/
```
+ 值也可以用百分数来设置，表示为盒子宽、高的百分之多少
+ 需要等比例设置的值，写auto

##### contain和cover
+ contain和cover是两个特殊的background-size的值
+ contain表示将背景图片智能改变尺寸以容纳到盒子里
+ cover表示将背景图片智能改变尺寸以撑满盒子

## 背景裁切
+ background-clip属性用来设置元素的背景裁切到哪个盒子，兼容到IE9

值|意义
-|-
border-box|背景延伸至边框
padding-box|背景延伸至内边padding不会绘制到边框处（仅在dotted、dashed边框可察觉）
content-box|背景被裁剪至内容区


## 背景固定
+ background-attachment属性决定背景图像的位置是在视口内固定，或者随着包含它的区块滚动

值|意义
-|-
fixed|自己滚动条不动，外部滚动条不动
local|自己滚动条动，外部滚动条动
scroll|自己滚动条不动，外部滚动条动（默认）


## 背景图片位置
+ background-position属性可以设置背景图片出现在盒子的什么位置
```
background-position:100px 200px;
```
+ 可以用top、bottom、center、left、right描述图片出现的位置

### CSS精灵
+ CSS精灵：将多个小图标合并制作到一张图片上，使用background-position属性单独显示其中一个，这样的技术叫做CSS精灵技术，也叫CSS雪碧图
+ CSS精灵可以减少HTTP请求数，加快网页显示速度。缺点也很明显：不方便测量、后期改动麻烦

## background综合属性
+ 一些常用的背景相关小属性，可以合写到一条background属性中
```
background: white url(images/archer.png) no-repeat center center;
/* 背景颜色 背景图片 背景重复 背景位置*/
```

## 线性渐变
+ 盒子的background-image属性可以用linear-gradient()形式创建线性渐变背景
```
background-image:linear-gradient(to right,blue,red);
/*渐变方向 开始颜色 结束颜色*/
```
+ 渐变方向也可以写成度数
```
background-image:linear-gradient(45deg,blue,red);
/*deg表示度数*/ 
```
+ 可以有多个颜色值，并且可以用百分数定义它们出现的位置
```
background-image:linear-gradient(to bottom,blue,yellow 20%,red);
/*yellow 中间色  20%出现的位置*/ 
```

#### 浏览器私有前缀
+ 不同浏览器有不同的私有前缀，用来对试验性质的CSS属性加以标识

品牌|前缀
-|-
Chrome|-webkit-
Firefox|-moz-
IE、Edge|-ms-
欧朋|-o-

## 径向渐变
+ 盒子的background-image属性可以用radial-gradient()形式创建径向渐变背景
```
background-image:radial-gradient(50% 50%,red,blue);
/*圆心坐标 */
```