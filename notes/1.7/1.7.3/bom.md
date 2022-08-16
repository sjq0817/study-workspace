## BOM是什么
+ BOM(browser object model),浏览器对象模型是JS与浏览器窗口交互的接口
+ 一些与浏览器改变尺寸、滚动条滚动相关的特效，都要借助BOM技术

### window对象
+ window对象是当前JS脚本运行所处的窗口，而这个窗口中包含DOM结构，window.document属性就是document对象
+ 在有标签页功能的浏览器中，每个标签都拥有自己的window对象；也就是说，同一个窗口的标签页之间不会共享一个window对象

### 全局变量是window的属性
+ 全局变量会成为window对象的属性
    ```
    var a = 10;
    console.log(window.a == a);//true
    ```

+ 意味着，多个js文件之间是共享全局作用域的，即js文件没有作用域隔离功能

### 内置函数普遍是window的方法
+ 如setInterval()、alert()等内置函数，普遍是window的方法
    ```
    console.log(window.alert == alert);//true
    console.log(window.setInterval == setInterval);//true
    ```

### 窗口尺寸相关属性

属性|意义
-|-
innerHeight|浏览器窗口的内容区域的高度，包含水平滚动条（如果有的话）
innerWidth|浏览器窗口的内容区域的宽度，包含垂直滚动条（如果有的话）
outerHeight|浏览器窗口的外部高度
outWidth|浏览器窗口的外部宽度


+ 获得不包含滚动条的窗口宽度，要用doucument.documentElement.clientWidth

#### resize事件
+ 在窗口大小改变之后，就会触发resize事件，可以使用window.onresize或者window.addEventListener('resize')来绑定事件处理函数

#### 已卷动高度
+ window.scrollY属性表示在垂直方向已滚动的像素值
+ document.documentElement.scrollTop属性也表示窗口卷动高度
    ```
    var scrollTop = window.scrollY || document.documentElement.scrollTop;
    ```

+ document.documentElement.scrollTop不是只读，而window.scrollY是只读的

#### scroll事件
+ 在窗口被卷动之后，就会触发scroll事件，可以使用window.onscroll或者window.addEventListener('scroll')来绑定事件处理函数


#### Navigator对象
+ window.navigator属性可以检索navigator对象，它内部含有用户此次活动的浏览器的相关属性和标识

属性|意义
-|-
appName|浏览器官方名称
appVersion|浏览器版本
userAgent|浏览器的用户代理(含有内核信息和封装壳信息)
platform|用户操作系统


#### History对象
+ window.history对象提供了操作浏览器会话历史的接口
+ 常用操作就是模拟浏览器回退按钮
    ```
    history.back();//等同于点击浏览器的回退按钮
    history.go(-1);//等同于history.back();
    ```

#### Location对象
+ window.location标识当前所在网址，可以通过给这个属性赋值命令浏览器进行页面跳转

#### 重新加载当前页面
+ 可以调用location的reload方法以重新加载当前页面，参数true表示强制从服务器强制加载

#### GET请求查询参数
+ window.location.search属性即为当前浏览器的GET请求查询参数


#### offsetTop属性
+ DOM元素都有offsetTop属性，表示此元素到定位祖先元素的垂直距离
+ 定位祖先元素：在祖先中，离自己最近的且拥有定位属性的元素