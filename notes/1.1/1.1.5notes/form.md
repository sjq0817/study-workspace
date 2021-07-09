#### 表单的创建
+ 表单用来收集信息，比如注册、登录、发送评论反馈、购买商品等等
+ 所有HTML表单都以一个form元素开始
```
<form action="save.php" method="post"></form>
<!--action属性表示表单要提交的后台程序的网址  method属性表示表单提交的方式，有get和post-->
```

#### 基本控件1
+ 单行文本框
    + 使用type属性值被设置为text的```<input>```元素可以创建单行文本框，他是一个单标签
    ```
    <input type="text">
    ```
    + value属性表示已经填好的值
    ```
    <input type="text" value="123">
    ```
    + placeholder属性表示提示文本，将以浅色文字写在文本框中，并不是文本框中的值
    ```
    <input type="text" placeholder="请输入姓名">
    ```
    + disabled属性表示用户不能与元素交互，即“锁死”
    ```<input type="text" disabled>```
+ 单选按钮
    + 使用type属性值被设置为radio的input元素可以创建单选按钮
    ```<input type="radio"> ```
    + 互斥的单选按钮应该设置它们的name为相同值
    + 单选按钮要有value属性，向服务器提交的就是value值
    + 单选按钮如果加上checked属性，表示默认被选中
+ label标签
    + label标签用来将文字和单选按钮进行绑定，用户单击文字的时候也视为点击了单选按钮
    ```
    <label>
        <input type="radio" name="sex" value="男" checked > 男
    </label>
    ```
    + 在html4时代，label标签是通过佛如属性和单选按钮的id属性进行绑定的
    ```
    <input type="radio" id="nan">
    <label for="nan">男</label>
    ```
+ 复选框
    + 使用type属性值被设置为checkbox的input元素可以创建复选框
    ```
    <input type="checkbox">

    ```
    + 同组复选框应该设置它们的name为相同值
    + 复选框要有value属性值，向服务器提交的就是value值
#### 基本控件2
+ 密码框
    + 使用type属性值被设置为password的```input```元素可以创建密码框
    ```
    <input type="password">
    ```
+ 下拉菜单
    + ```<select>```标签表示下拉菜单，```<option>```是它内部的选项
        ```
        <select>
            <option value="alipay">支付宝</option>
            <option value="wechat">微信</option>
            <option value="bank">网银</option>
        </select>
        ```

+ 多行文本框
    + ```<textarea></textarea>```表示多行文本框
    + rows和cols属性，用于定义多行文本框的行数和列数

+ 三种按钮
    + 表单中常见三种按钮，它们也都是input标签，type属性值不同

        type属性值|按钮种类
        ----|----
        button|普通按钮，可以简写为```<button></button>```
        submit|提交按钮
        reset|重置按钮

#### 总结

type属性值|控件
----|----
text|单行文本框
radio|单选按钮
checkbox|多选按钮
password|密码框
button|普通按钮
reset|重置按钮
submit|提交按钮

#### 更丰富的input种类 兼容到IE9

type属性|控件
----|----
color|颜色选择控件
data、time|日期、时间选择控件
email|电子邮件输入控件
file|文件选择控件
number|数字输入控件
range|拖拽条
search|搜索条
url|网址输入控件

+ required属性  表示必填

#### datalist控件
+ datalist控件可以为输入框提供一些必选1项，当用户输入的内容备选项文字相同时，将会显示智能感应
```
<input type="text" list="province-list">
<datalist id="province-list">
    <option value="山西">山西</option>
    <option value="湖北">湖北</option>
    <option value="上海">上海</option>
    <option value="北京">
</datalist>
```