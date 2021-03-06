#### 图片标签
+ img标签用来在网页中插入图片
```
<img src="images/gugong.jpg">   <!--img是image的缩写 src是source的缩写-->
```
+ 图片必须复制到项目文件夹中，一般将图片保存到项目文件夹中的images文件夹中。
+ 图片后缀名一定要写
+ 图片本质上没有被插入到网页中，只是被引入到了网页中
    #### img标签的alt属性
    + alt属性是alternate“替代品”的缩写，它是对图像的文本描述，不是强制性的
    ```
    <img src="images/gugong.jpg" alt="故宫角楼">
    ```
    + 如果由于某种原因无法加载图像，浏览器会在页面上显示alt属性中的备用文本
    + 使用网页朗读时，也会朗读alt属性中的文本

    #### img标签的width、height属性
    + width、height属性分别设置宽度和高度，单位时像素，但是不需要写单位
    ```
    <img src="images/gugong.jpg" alt="故宫角楼" width="300" height="100">
    <!--不赋值默认按图片原始像素展开 -->
    ```
    #### 网页上支持的图片格式
    格式|说明
    --|--
    .bmp|windows画图软件默认保存的格式，位图 广度不足
    .gif|支持动画（比如表情包）
    .jpeg(.jpg)|有损压缩图片，用于照片
    .png|便携式网络图像，用于logo、背景图姓等，支持透明和半透明，支持有损和无损
    .svg|矢量图片，不会出现锯齿
    .webp|最新的压缩算法非常优秀的图片格式，来自google
    #### 相对路径
    + 相对路径：描述从网页出发，如何找到图片
    ```
    <img src="images/gugong.jpg" >
    ```
    + 随着网页和图片的位置关系不同，插入图片的代码随之改变
    + 如果需要回退层级，使用"../"这样的写法
    #### 绝对路径
    + 绝对路径：描述图片的精准位置
    ```
    <img src="https://www.imooc.com/static/img/index/logo-recommended.png">
    ```
    + 不管网页在哪里，绝对路径不需要改变
#### 超级链接
+ 超级链接是将网页和网页连接到一起的方法，是互联网成“网”的原因
+ 使用a标签制作超级链接
```
<a herf="2.html">去第二个网页</a>
<!--a是anchor锚 hypertext reference 超文本引用-->
```
#### href属性支持相对路径和绝对路径
+ href属性支持相对路径和绝对路径
```
<a href="web/2.html">去第二个网页</a>
<a href="../web/2.html">去第二个网页</a>
<a href="https://www.imooc.com">去慕课</a>
```
#### a标签的title属性
+ a标签的title属性用于设置鼠标的悬停文本
```
<a href="2.html" title="点我">去第二个网页</a>
```

#### 在新窗口中打开网页
+ 将a标签的target属性设置为blank，即可在新标签页中打开网页
```
<a href="2.html" target="blank">去第二个网页</a>
<!--HTML5 -->
<a href="2.html" target="_blank">去第二个网页</a>
<!--HTML4 -->
```
#### 给图片设置超级链接
+ 图片也可以设置超级链接，只需要用a标签包裹img标签即可
```
<a href="2.html">
    <img src="web/2.jpg">
</a>
```
#### 页面内锚点
+ 较长的页面，可以适当的给h系列标签添加id属性，它将成为页面的"锚点"
```
<h1 id="wuxi">无锡美景</h1>
```
+ 当网址后面添加#时，页面将自动滚动到锚点所在位置
+ 其他页面的超级链接，可以链接到指定锚点
```
<a href="lvyou.html#wuxi">去看无锡美景</a>
<a id="#top">返回顶部</a><!-- html5特色直接回顶部，天生可以使用-->
``` 
#### 下载链接
+ 指向exe、zip、rar等文件格式的链接，将自动成为下载链接
```
<a href="1.zip">下载</a>
```
#### 邮件链接、电话链接
+ 有mailto:前缀的链接是邮件链接，系统将自动打开Email相关软件
```
<a href="mailto:me@test.com">给小编发邮件</a>
```
+ 有tel:前缀的链接是电话链接，系统将自动打开拨号盘
```
<a href="tel:12306">打电话买火车票</a>
```
#### 音频和视频
+ 以前在网页中插入音频和视频需要借助Flash，现在Flash技术快要被淘汰，在HTML5网页中可以轻松插入音频和视频
#### 音频
+ 在浏览器中插入音频需要使用audio标签，兼容到IE9
```
<audio controls src="音频地址">不支持播放音频</audio>
<!--controls 显示播放控件 高级浏览器文字不显示-->
```
+ 常用音频格式mp3和ogg格式
#### autoplay属性
+ 声明autoplay属性，音频会自动播放
+ 常用浏览器为了不打扰用户，可能会不允许自动播放音乐，必须让用户动手点击之后才能播放
#### loop属性
+ 声明loop属性，将会自动循环播放音频
```
<audio src="" controls autoplay loop></audio>
```
#### 视频
+ 在浏览器中插入视频需要使用video属性，兼容到IE9
```
<video controls src="视频地址" loop autoplay>不支持视频播放</video>
<!--如果浏览器支持播放文字不显示 -->
```
+ 常用视频格式mp4、ogv、webm等格式
#### 区块标签
+ div标签实现文档区块分割
    + 以前，为了区分每个div的功能，会借助div标签的class属性
    + 现今，HTML5推出了众多新区块标签

        区块标签|说明
        ----|----
        ```<section>```|文档的区域，语义比div大
        ```<article>```|文档的核心文章内容，会被搜索引擎主要抓取
        ```<aside>```|文档的非必要相关内容，比如广告等
        ```<nav>```|导航条
        ```<header>```|页头
        ```<main>```|网页核心部分
        ```<footer>```|页脚

#### 语义化标签
+ ```<span>```标签是文本中的“区块”标签，本身没有任何特殊的显示效果，可以结合css来丰富样式
+ ```<b>、<u>、<i>```标签充满浓浓的“样式”意味，已经被css代替，但是在网页中也可以表示需要强调的文本

    标签|说明
    ---- | ----
    ```<b>``` | 被加粗的文字
    ```<u>``` | 加下划线的文字
    ```<i>``` | 倾斜的文字

+ ```<strong>、<em>、<mark>```标签均表示强调语义

    标签|说明
    ---- | ----
    ```<strong>``` | 代表特别重要文字
    ```<em>``` | 代表强调文字
    ```<mark>``` | 代表一段需要被高亮的文字

+ ```<figure> <figcaption>```标签
    + ```<figure>```元素代表一段独立的内容，说明```<figcaption>```配合使用，它是一个独立的引用单元你，比如建议读者拓展视野的图片等，当着部分转移到附录中或其他页面时不会影响到主体 