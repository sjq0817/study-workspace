#### 标签选择器
+ 标签选择器也称为元素选择器、类型xzq，它直接使用元素的标签名当做选择器，将选择页面上所有该种标签
```
span {
    color: red;
}
/*选择所有的span*/
```
+ 标签选择器将选择页面所有该种标签，无论这个标签所处位置的深浅
+ 标签选择器覆盖面非常大，通常用来标签的初始化
```
ul{
    /*去掉无序列表的小圆点*/
    list-style: none;
}
a {
    /*去掉a标签的下划线*/
    text-decoration: none;
}
```
#### id选择器
+ 标签可以有id属性，是这个标签的唯一标识
+ id的名称只能由字母、数字、下划线、短横构成，且不能以数字开头，字母区分大小写，但习惯上一般为小写字母
+ CSS选择器可以使用#（井号）前缀，选择指定id的标签
```
#para1 {
    color: red;
}
```

#### class选择器
+ class属性表示"类名"
+ 命名规则与id选择器相同
+ 使用.(点)前缀选择指定的class选择器
+ 多个标签可以为相同的类名
+ 同一个标签可以同时属于多个类，类名用空格隔开
```
<p class="warning spec">我是段落</p>

.warning {
    color: red;
}
.spec {
    font-style: italic;
}
```
#### 原子类
+ 在做网页项目前，可以将所有的常用字号、文字颜色、行高、外边距、内边距等都设置为单独的类
+ HTML标签就可以“则需选择”它的类名，就可以非常快速的添加一些常见样式

#### 复合选择器

选择器名称|示例|示例的意义
--|--|--
后代选择器|.box .spec|选择类名为box的标签内部的类名为spec的标签
交集选择器|li.spec|选择既是li标签，也属于spec类的标签
并集选择器|ul,ol|选择所有ul和ol标签

#### 后代选择器
+ 在CSS选择器中，使用空表示'后代'
```
.box p{
    color: red;
}
<div class="box">
    <p>我是盒子中的段落</p>
</div>
<!--“后代”不一定是“儿子” -->
<div class="box">
    <ul>
        <li>
            <p>我是盒子中的段落</p>
        </li>
    </ul>
    
</div>
```
#### 交集选择器
```
h3.spec {
    color: red;
}


<p class="spec">我没有被选择</p>
<h3 class="spec">我被选择了</h3>
```

#### 并集选择器
```
ul,ol{ 
    list-style: none;
}

<ul>
    <li>去掉小圆点</li>
</ul>
<ol>
    <li>去掉小圆点</li>
</ol>
```
#### 伪类
+ 伪类是添加到选择器的描述性词语，指定要选择的元素的特殊状态，超级链接拥有4个特殊状态

伪类|意义
--|--
a:link|没有被访问的超级链接
a:visited|已经被访问过的超级链接
a:hover|正被鼠标悬停的超级链接
a:active|正被激活的超级链接（按下按键还没松开按键）

+ 必须按照顺序不然可能不会生效即lvha

#### 元素关系选择器

名称|举例|意义
--|--|--
子选择器|div>p|div的子标签p
相邻兄弟选择器|img+p|图片后面紧跟着的段落将被选中
通用兄弟选择器|p~span|p元素之后的所有同层级的span元素

+ 子选择器只选择子标签,从IE7兼容
```
.box>p {
    color:
}

<div class="box">
    <p>我被选择了</p>
    <div>
        <p>我没有被选择</p>
    </div>
</div>
```
+ 相邻兄弟选择器(+)介于两个选择器之间，当第二个元素紧跟在第一个元素之后，并且两个元素都是属于同一个父元素的子元素，则第二个元素将被选中
```
img+span{
    color: red;
}

<p>
    <img src="images/0.jpg" alt="">
    <span>我被选中了</span>
    <span>我没有被选中</span>
</p>
<span>我也没有被选中</span>
```
+ 通用兄弟选择器(~),a~b选择a元素之后所有同层级b元素,从IE7兼容
```
h3~span{
    font-style: italic;
}


<span>我没被选择</span>
<h3>三级标题</h3>
<span>选中</span>
<p>不选</p>
<span>选中</span>
<div>
    <span>不选</span>
</div>
```

#### 序号选择器

举例|意义|兼容性
--|--|--
:first-child|第一个子元素|IE7
:last-child|最后一个子元素|IE9
:nth-child(3)|第3个子元素|IE9
:nth-of-type(3)|第3个某类型子元素|IE9
:nth-last-child(3)|倒数第3个子元素|IE9
:nth-last-of-type(3)|倒数第3个某类型子元素|IE9

```
.box p:last-child{
    color: red;

}

.box1 p:nth-child(3n + 2){
    color: green;
}
/*2、5、8...*/
```

#### 属性选择器

举例|意义
--|--
img[alt]|选择有alt属性的img标签
img[alt="故宫"]|选择alt属性是故宫的img标签
img[alt^="北京"]|选择alt属性以北京开头的img标签
img[alt$="夜景"]|选择alt属性以夜景结尾的img标签
img[alt*="美"]|选择有alt属性中含有美字的的img标签
img[alt~="手机拍摄"]|选择有alt属性中有空格隔开的手机拍摄字样的img标签
img[alt|="参赛作品"]|选择有alt属性以“参赛作用-”开头的img标签

#### CSS新增伪类

伪类|意义
--|--
:empty|选择空标签
:focus|选择当前获得焦点的表单元素
:enabled|选择当前有效的表单元素
:disabled|选择当前无效的表单元素
:checked|选择当前已经勾选的单选按钮或者复选框
:root|选择根元素，即html标签

#### 伪元素
+ CSS3新增了伪元素特性，顾名思义，表示虚拟动态创建的元素
+ 伪元素用双冒号表示，IE8可以兼容单冒号
+ ::befor 创建一个伪元素，将其成为匹配选中的元素的第一个子元素，必须设置content属性表示其中的内容
+ ::after 创建一个伪元素，将其成为匹配选中的元素的最后一个子元素，必须设置content属性表示其中内容
+ ::selection CSS伪元素应用与文档中被用户高亮的部分（使用鼠标选中的部分）
+ ::first-letter会选中某元素中（必须是块级元素）第一行的第一个字母
+ ::first-line会选中某元素中（必须是块级元素）第一行全部文字

#### 层叠性和权重计算
+ 层叠性：多个选择器可以同时作用于同一个标签，效果叠加
+ 层叠性的冲突问题；id权重 >class权重 >标签权重
+ 复杂选择器权重计算；复杂选择器可以通过（id个数，class的个数，标签的个数）的形式，计算权重
+ ！important 如果需要将某个选择器的某条属性提升权重，可以在属性后面写！important