## DOM
+ DOM Document Object Model,文档对象模型，是JavaScript操作HTML文档的接口，使文档操作变得非常优雅、简便
+ DOM将文档表示为节点树
## node Type常用属性值
+ 节点的nodeType属性可以显示这个节点具体的类型

nodeType值|节点类型
-|-
1|元素节点，```<p><div>```
3|文字节点
8|注释节点
9|document节点
10|DTD节点，文档类型声明

#### 访问元素节点
+ 所谓访问元素节点，就是指得到，获取页面上的元素节点
+ 访问元素节点使用document对象
#### document对象
+ 几乎所有的DOM的功能都封装在了document对象中
+ document对象也表示整个HTML文档，它是DOM节点树的根
+ document对象的nodeType属性值是9


#### 访问元素节点的常用方法

方法|功能|兼容性
-|-|-
document.getElementById()|通过id得到元素|IE6
document.getElementsByTagName()|通过标签名得到元素数组|IE6
document.getElementByClassName()|通过类名得到元素数组|IE9
document.querySelector()|通过选择器得到元素|IE8部分兼容，IE9完全兼容
document.querySelectorAll()|通过选择器得到元素数组|IE8部分兼容，IE9完全兼容


+ 如果页面上有相同的id则只能得到一个
+ 不管层级多深，都可以通过id找到

+ 数组方便遍历，从而可以批量操控元素节点
+ 即使页面上只有一个指定标签名的节点，也将得到长度为1的数组
+ 任何一个节点元素也可以调用getElementsByTagName()方法，从而得到其内部的某种类的元素节点

+ querySelector()方法只能得到页面上一个元素，如果有多个元素符合条件，则只能得到第一个元素
+ querySelector()方法从IE8开始兼容，但从IE9开始支持CSS3的选择器，如：nth-child(),:[src^='dog']等CSS3选择器形式都支持良好
#### 延迟允许
+ js代码一定要写到HTML节点的后面，否则无法找到相应HTML节点
+ 可以使用window.onload = function(){}事件，使页面加载完毕后，再执行指定的代码

#### 节点的关系
+ firstChild得到第一个子节点
+ lastChild得到最后一个子节点
+ childNodes得到的子节点
+ 子节点使用parentNode访问父节点
+ nextSibling 访问下一个兄弟节点
+ previousSibling 访问上一个兄弟节点

+ DOM中，文本节点也属于节点，在使用节点的关系时一定要注意
+ 再标准的W3C规范中，空白文本节点也应该算作节点，但是在IE8及以前的浏览器中会有一定的兼容问题，它们不把空文本节点当做节点

#### 排除文本节点的干扰
+ 从IE9开始支持一些“只考虑元素节点”的属性

关系|考虑所有节点|只考虑元素节点
-|-|
子节点|childNodes|children
父节点|parentNode|parentNode
第一个子节点|firstChild|firstElementChild
最后一个子节点|lastChild|lastElementChild
前一个兄弟节点|previousSibling|previousElementSibling
后一个兄弟子节点|nextSibling|nextElementSibling

#### 书写常见的节点关系函数
+ 书写IE6也能兼容的寻找所有元素子节点函数
+ 书写IE6也能兼容的寻找前一个元素兄弟节点函数
+ 如何编写函数，获得某元素的所有的兄弟节点

#### 改变元素节点中的内容
+ 改变元素节点中的内容可以使用两个相关属性
    + innerHTML属性能以HTML语法设置节点中的内容
    + innerText属性只能以纯文本的形式设置节点中的内容

#### 改变元素节点的css样式
+ 改变元素节点的css样式需要使用这样的语句(css属性要写成驼峰的形式，属性值要设置成完整形式，注意单位)
    ```
    oBox.style.backgroundColor = 'red';
    oBox.style.backgroundImage = 'url(image/1.jpg';
    oBox.style.fontSize = '32px';
    ```


#### 改变元素节点的HTML属性
+ 标准W3C属性，如src，href等等，只需要直接打点进行更改即可
    ```
    oImag.src = 'images/2.jpg';

    ```
+ 不符合W3C标准的属性，要使用setAttribute()和getAttribute()来设置、读取


## 节点的创建
+ document.createElement()方法用于创建一个指定tagname的HTML元素
    ```
    var oDiv = document.createElement('div');
    ```
+ 新创建出的节点是孤儿节点，这意味着它并没有被挂载都DOM树上，我们无法看见它
+ 必须继续使用appendChild()或insertBefore()方法将孤儿节点插入到DOM树上
+ 任何已经在DOM树上的节点，都可以调用appendChild()方法，它已经将孤儿节点挂载到它内部，成为它最后一个子节点
    ```
    父节点.appendChild(孤儿节点);
    ```
+ 任何已经在DOM树上的节点，都可以调用insertBefore()方法。它可以将孤儿节点挂载到它内部，成为它的标杆子节点之前的节点
    ```
    父节点.insertBefore(孤儿节点,标杆节点);
    ```

### 移动节点
+ 如果将已经挂载到DOM树上的节点成为appendChild()或者insertBefore()的参数，这个节点将会被移动
    ```
    新父节点.appendChild(已经有父亲的节点);
    新父节点.insetrBefore(已经有父亲的节点,标杆子节点);
    ```
+ 这意味着一个节点不能同时位于DOM树的两个位置
### 删除节点
+ removeChild()节点从DOM中删除一个子节点
    ```
    父节点.removeChild(要删除子节点)；
    ```

+ 节点不能主动删除自己，必须由父节点删除它

### 克隆节点
+ cloneNode()方法可以克隆节点。克隆出的节点是“孤儿节点”
    ```
    var 孤儿节点 = 老节点.cloneNode();
    var 孤儿节点 = 老节点.cloneNode(true);
    ```

+ 参数是一个布尔值，表示是否采用深度克隆：如果为true，则该节点的所有后代节点也都会被克隆，如果为false，则只克隆该节点本身

## 事件监听
+ DOM允许我们书写JavaScript代码以让HTML元素对事件做出反应
+ 什么是“事件”：用户与网页的交互动作
+ “监听”就是让计算机随时能够发现这个事件发生了，从而执行程序员预先编写的程序
+ 设置事件监听的方法主要有onxxx和addEventListener()两种

##### 简单的设置事件监听的方法
+ 设置它们的onxxx属性。
    ```
    oBox.onclick = function (){
        //点击盒子时，将执行这里的语句
    }
    ```

##### 常见的鼠标事件监听
事件名|事件描述
-|-
onclick|当鼠标单击某个对象
ondbclick|当鼠标双击某个对象
onmousedown|当某个鼠标按键在某个对象上被按下
onmouseup|当某个鼠标按键在某个对象上被松开
onmousemove|当某个鼠标按键在某个对象上被移动
onmouseenter|当鼠标进入某个对象
onmouseleave|当鼠标离开某个对象

##### 常见的键盘事件监听

事件名|事件描述
-|-
onkeypress|当某个键盘的键被按下（系统按钮如箭头键和功能键无法得到识别）
onkeydown|当某个键盘的键被按下（系统按钮可以识别，并且会先于onkeypress发生）
onkeyup|当某个键盘的键被松开 


##### 常见的表单事件监听

事件名|事件描述
-|-
onchange|当用户改变域的内容
onfocus|当某元素获得焦点（比如tab键或鼠标点击）
onblur|当某元素失去焦点
onsubmit|当表单被提交
onreset|当表单被重置
oninput|当用户正在改变域的内容

##### 常见的页面事件监听
事件名|事件描述
-|-
onload|当页面或图像被完成加载
onunload|当用户退出页面



## 事件传播

+ 先从外到内，然后再从内到外
+ 捕获截断(capturing phase)
+ 冒泡阶段(bubbling phase)
+ onxxx这样的写法只能监听冒泡阶段

##### DOM0级事件监听
+ 只能监听冒泡阶段
    ```
    oBox.onclick = function(){

    };
    ```
##### DOM2级事件监听
+ true监听捕获阶段，false监听冒泡阶段
    ```
    oBox.addEventListener('click',function(){

    },true);
    ```

#### 注意
+ 最内部元素不再区分捕获和冒泡阶段，会先执行写在前面的监听，然后执行后写的监听
+ 如果给元素设置相同的两个或多个同名事件，则DOM0级写法后面写的会覆盖先写的而DOM2级会按顺序执行

## 事件对象
+ 事件处理函数提供一个形式参数，它是一个对象，封装了本次事件的细节
+ 这个参数通常用单词event或字母e来表示
    ```
    oBox.onmousemove = function (e){
        //对象e就是这次事件的’事件对象‘
    };
    ```

##### 鼠标位置

属性|属性描述值
-|-
clientX|鼠标指针相当于浏览器的水平坐标
clientY|鼠标指针相对于浏览器的垂直坐标
pageX|鼠标指针相对于整张网页的水平坐标
pageY|鼠标指针相对于整张网页的垂直坐标
offsetX|鼠标指针相对于事件源元素的水平坐标
offsetY|鼠标指针相对于事件源元素的垂直坐标

#### e.charCode和e.keyCode属性
+ e.charCode属性通常用于onkeypress事件中，表示用户输入的字符的’字符码‘
+ e.keyCode属性通常用于onkeydown事件和onkeyup中，表示用户按下的按键的键码

##### charCode字符码
字符|字符码
-|-
数字0~9|48~57
大写字母A~Z|65~90
小写字母a~z|97~122

##### keyCode键码
按键|键码
-|-
数字0~9|48~57
字母不分大小写|一律65~90
四个方向键←↑→↓|37，38，39，40
回车键|13
空格键|32

##### e.preventDefault()方法
+ e.preventDefault()方法用来阻止事件产生的默认动作
+ 一些特殊的业务需求，需要阻止事件的默认动作

##### 鼠标滚轮事件
+ 鼠标滚轮事件时onmousewheel,它的事件对象e提供deltaY属性表示鼠标滚动方向，向下滚动时返回正值，向上滚动时返回负值

##### e.stopPropagation()方法
+ e.stopPropagation()方法用来阻止事件继续传播
+ 在一些场合，非常有必要切断事件继续传播，否则会造成页面特效显示bug



##### 批量添加事件监听
##### 性能问题
+ 每一个事件监听注册都会消耗一定的系统内存，而批量添加事件会导致监听数量太多，内存消耗会非常大
+ 实际上，每个li的事件处理函数都是不同的函数，这些函数本身也会占用内存
##### 新增元素动态绑定事件
+ 新增元素必须分别添加事件监听，不能自动获得事件监听
+ 大量事件监听、大量事件处理函数都会产生大量消耗内存

## 事件委托
+ 利用事件冒泡机制，将后代元素事件委托给祖先元素

#### e.target和e.currentTarget属性
+ 事件委托通常需要结合使用e.target属性

属性|属性描述
-|-
target|触发此事件的最早元素，即“事件源元素”
currentTarget|事件处理程序附加到的元素
 

##### 事件委托的使用场景
+ 当有大量类似元素需要批量添加事件监听时。使用事件委托可以减少内存开销
+ 当有动态元素节点上树时，使用事件委托可以让新上树的元素具有事件监听

##### 使用事件委托时需要注意的事项
+ onmouseenter和onmouseover都表示’鼠标进入‘，它们有什么区别？
    + onmouseenter不冒泡,onmouseover冒泡

+ 使用事件委托时要注意：不能委托不冒泡的事件给祖先元素

+ 最内层元素不能再有额外的内层元素了


## 定时器
+ setInterval()函数可以重复调用一个函数，在每次调用之间具有固定的时间间隔
    ```
    setInterval(function(){
        //这个函数将自动被以固定间隔时间（毫秒）调用
    },2000);
    ```

##### 函数的参数
+ setINterval()函数可以接收第3、4....个参数，它们将按顺序传入函数
    ```
    setInterval(function(a,b){
        //形式参数a的值是88，形式参数b的值是66
    },2000,88,66);

    ```

+ 具名函数也可以传入setInterval
    ```
    var a = 0;
    function fun(){
        consloe.log(==a);
    }
    setInterrval(fun,1000);
    ```
##### 清除定时器
+ clearInterval()函数可以清除一个定时器
    ```
    //设置定时器，并且用timer变量接收这个定时器
    var timer = setInterval(function(){

    },2000);
    //点击按钮时，清除定时器
    oBtn.onclick = function(){
        clearInterval(timer);
    }
    ```

## 延时器
+ setTimeout()函数可以设置一个延时器，当指定时间到了之后，会执行函数一次，不再重复执行
    ```
    setTimeout(function(){
        //这个函数会在2秒后执行一次
    },2000);

    ```
+ clearTimeout()函数可以清除延时器，和clearInterval()类似

## 异步(asynchronous)
+ 异步：不会阻塞CPU继续执行其他语句，当异步完成时，会执行“回调函数”(callback)


## 使用定时器实现动画
+ 使用定时器实现动画较为不便：
    + 不方便根据动画总时间计算步长
    + 运动方向要设置正负
    + 多种运动进行叠加较为困难（比如一个方形一边移动一边变为圆形）



## js和css3结合实现动画
+ CSS3的transition过渡属性可以实现动画
+ JS可以利用CSS3的transition属性轻松实现元素动画
+ JS和CSS3结合实现动画规避了定时器制作动画的缺点



## 函数节流
+ 一个函数执行一次后，只有大于设定的执行周期后才允许执行第二次
+ 函数节流非常容易实现，只需要借助setTimeout()延时器
    ```
    var lock = true;
    function 需要节流的函数(){
        //如果锁是关闭状态，则不执行
        if(!lock) return;
        //函数核心语句
        //关锁
        lock = false;
        //指定毫秒数后将锁打开
        setTimeout(function(){
            lock = true;
        },2000);
    }

    ```










































