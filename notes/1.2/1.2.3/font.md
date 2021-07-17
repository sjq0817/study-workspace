#### 常用文本样式属性
+ color属性可以设置文本内容的前景色
    + color属性主要可以用英语单词、十六进制、rgb()、rgba();
    + 英语单词学习时临时使用
    ```
    /*十六进制*/
    color: #ff0000;
    /*rgb()*/
    color: rgb(255,0,0);
    /*rgba()   a表示透明度*/
    color: rgba(255,0,0,.065;
    ```
+ font-size属性用来设置字号，单位通常为px。还有em、rem单位
    + 网页文字正文号通常是16px，浏览器最小支持是10px
+ font-weight属性设置字体的粗细程度，通常就用normal和bold两个值

    示例|意义
    --|--
    font-weight: normal;|正常粗细，与400等值
    font-weight: bold;|加粗，与700等值
    font-weight: lighter;|更细，大多数中文字体不支持
    font-weight: bolder;|更粗，大多数中文字体不支持

+ font-style属性设置字体倾斜

    示例|意义
    --|--
    font-style: normal;|取消倾斜，比如把天生倾斜的i、em等标签设置为不倾斜
    font-style: italic;|设置为倾斜字体
    font-style: oblique;|设置为倾斜字体（用常规字体模拟，不常用）

+ text-decoration属性用于设置文本的修饰线外观的

    示例|意义
    --|--
    text-decoration: none;|没有修饰线
    text-decoration: underline;|下划线
    text-decoration: line-through;|删除线


#### 字体属性详解
+ font-family属性用于设置字体
```
font-family:"微软雅黑";
```
+ 字体可以是列表形式，一般英语字体放到最前面，后面字体是前面字体的后备字体
```
font-family:serif,"Times New Roman","微软雅黑";
```
+ 中文字体可以用英文名字代替
+ 字体必须是用户计算机已经安装好的字体。
+ 如果用户计算机没有字体，可以让用户加载网页的时候会同时下载这些字体文件
+ 定义字体格式，eot、woff2、woff、ttf、svg，
+ 在拥有字体文件后，就可以用@font-face定义字体


#### 段落和行相关属性
+ text-indent属性定义首行文本内容之前的缩进量，缩进两个字符应该写作,em表示字符宽度
```
text-indent: 2em;
```
+ line-height属性用于定义行高，以px为单位数值。也可以是没有单位的数值，表示字号的倍数(推荐)。也可以是百分数，表示字号的倍数。
```
line-height: 30px;
line-height: 1.5;
line-height: 150%;
```
+ 单行文本垂直居中，设置行高=盒子高度，即可实现单行文本垂直居中
+ 设置text-align: center;即可实现文本水平居中
+ font合写属性
    font属性可以用来作为font-style、font-weight,font-size,line-height,font-family属性的合写
    ```
    font: italic bold 20px/1.5 Arial,"微软雅黑";
    ```

#### 继承性
+ 文本相关的属性普遍具有继承性，只需要给祖先标签设置，即可在后代所有标签中生效
+ color、font-、list-、text-、line-
+ 因为文字相关属性具有继承性，所以通常会设置body标签的字号、颜色、行高等，这样就能当作整个网页的默认样式了。
+ 就近原则