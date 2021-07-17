#### 盒模型
+ 什么是盒模型？所有的HTML标签都可以看成巨星盒子。由width、height、padding、border构成，称为“盒模型”
+ width、height表示内容的高宽
+ padding内边距，border边框
+ 盒子的总宽度=width+左右padding+左右border
+ 盒子的总高度=height+上下padding+上下border
```
width:200px;
height:200px;
border: 10px solid red;
padding:10px;
```

#### padding是盒子的内边距
+ padding是盒子内边距，即盒子边框内壁到文字内容的距离
+ 四个方向的padding，可以分别用小属性进行设置

    小属性|意义
    --|--
    padding-top|上padding
    padding-right|右padding
    padding-bottom|下padding
    padding-left|左padding

+ padding属性如果用四个数值以空格隔进行设置，分别表示上、右、下、左的padding
+ padding属性如果用三个数值以空格隔进行设置，分别表示上、左右、下的padding
+ padding属性如果用两个数值以空格隔进行设置，分别表示上下、左右的padding
```
padding: 10px 20px 10px 20px;
padding: 10px 20px 10px;
padding: 10px 20px;
```

#### margin是盒子的外边距
+ margin是盒子的外边距，即盒子和其他盒子之间的距离
+ margin也有四个方向

    小属性|意义
    --|--
    margin-top|上margin，向上踹
    margin-right|右margin，向右踹
    margin-bottom|下margin，向下踹
    margin-left|左margin，向左踹

#### margin的塌陷
+ 竖直方向的margin有塌陷现象：小的margin会塌陷到大的margin中，从而margin不叠加，只以大值为准
+ 水平方向不叠加

#### 一些元素默认的margin
+ eg：body、ul、p等，清除
```
* {
    margin:0;
    padding:0;
    /*  *通配符选择器，表示选择所有元素*/
}
body,ul,p {
    margin:0;
    padding:0;
}
/*通配符有效率问题，应该使用并集选择器*/
```

#### 盒子的水平居中
+ 将盒子左右两边的margin都设置为auto，盒子将水平居中
```
margin: 0 auto;
```
+ 文本居中和盒子居中是两个概念


#### 盒模型计算
#### box-sizing属性，兼容到IE9
+ 将盒子添加了box-sizing：border-box;之后，盒子的width、height数字就表示盒子实际占有的宽高(不含margin)了，即padding、border变为内缩，不再外扩
+ box-sizing属性大量应用于移动网页制作中，因为它结合百分比布局、弹性布局等非常好用，在PC页面开发中使用较少

#### display属性(默认)
#### 行内元素和块级元素

display属性类型|是否能并排设置|是否能设置宽高|当不设置width属性时|举例
--|--|--|--|--
块级元素|否|是|width自动撑满|div、section、header、h系列、li、ul
行内元素|是|否|width自动收缩|a、span、em、h、u、i


#### 行内块
+ img和表单元素是特殊的行内块，它们既能够设置宽度高度，也能够并排显示


#### 行内元素和块级元素的相互转换
+ 使用display:block;即可将元素转换块级元素
+ 使用display:inline;即可将元素转换为行内元素，将元素转为行内元素的应用不多见
+ 使用display:inline-block;即可将元素转为行内块


#### 元素的隐藏
+ 使用display: none;可以将元素隐藏，元素将彻底放弃位置，如同没有写它的标签一样
+ 使用visibility: hidden;可以将元素隐藏，但是元素不放弃自己的位置