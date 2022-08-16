### 基本数据类型
##### typeof运算符
+ 使用typeof运算符可以检测值或者变量的类型
```
typeof 5; //查看5的数据类型控制台
console.log(typeof 5); //HTML中
```
+ 5种基本数据类型的typeof检测结果
 
 类型名|typeof检测结果|值举例
 -|-|-
 数字类型|number|5
 字符串类型|string|'慕课网'
 布尔类型|boolean|true
 undefined类型|undefined|undefined
 null类型|object|null

#### Number（数字）类型
+ 所有数字不分大小、不分整浮、不分正负、都是数字类型
+ eg： 925 、3.13 、 -9
+ 小数中0可以省略
+ eg： 0.5可写作.5但6.8不可这样写
##### 科学计数法
+ 较大数或较小数（绝对值较小）可以写成科学计数法
+ 3e8=300000000、3e-4=0.0003
##### 不同进制的数字
+ 二进制数值以0b开头
```
0b10 //2
```
+ 八进制数值以0开头
+ 十六进制数值以0x开头
##### 一个特殊的数字型值NaN
+ NaN是英语“not a number”的意思，但它不是一个数字类型的值
```
typeof NaN;//number
```
+ 0除以0的结果是NaN，事实上，在数学运算中，若结果不能得到数字，其结果往往都是NaN
+ NaN不自等

#### String 字符串类型
+ 字符串要用引号包裹，双引号或者单引号均可
+ 数字11和字符串'11'语义不同，前者是数量，后者是文本
+ 加号可以用来拼接多个字符串
##### 字符串和变量的拼接
+ 要将一个变量的值‘插入’到字符串中，要“斩断链接”
```
var year =2022;
var str = '北京冬季奥运会' + year + '年召开'
```
##### 空字符串
+ 直接书写闭合的引号即可
##### 字符串的length属性
+ 字符串的length属性表示字符串的长度
```
'我喜欢JS'.length; //5
''.length;//0
'我喜欢JS，我也喜欢HTML'.length;//14
```
##### 字符串的常用方法
+ “方法”就是能够打点调用的函数，字符串有丰富的方法

方法|功能
-|-
charAt()|得到指定位置的字符
substring()|提取子串
substr()|提取子串
slice()|提取子串
toUpperCase()|将字符串变为大写
toLowerCase()|将字符串变为小写
indexOf()|检索字符串

```
var str='我喜欢JS，我也喜欢HTML';//索引从0开始
str.charAt(0);//我，找到0号位置的字符
str.substring(3,5);//JS,从3号位置到5号位置不包括5
str.substring(12);//ML，从12到最后
str.substring(5,3);//JS,会自动调整为小数在前
str.substr(3,2);//JS，从3开始的长度为2的子串
str.substr(12);//ML,后面数字可省略，表示到字符串结尾
str.substr(-2,2);//ML，前面一个数可以是负数，表示倒数位置
str.slice(3,5);//JS,从3开始到5结束，不包括5处的子串
str.slice(-4,-1);//HML,前面参数必须小于后面参数

```
+ 对比总结
    + substring(a,b)和slice(a,b)功能基本一致，都是得到从a开始到b结束（不包括b）的子串
    + 区别
        + substring()可以自动交换两个参数位置，而slice()不行
        + slice()的参数a可以是负数，而substring()不行


+ indexOf()函数
    + indexOf()方法返回某个指定的字符串值在字符串中首次出现的位置
    + 如果要检索的字符串值没有出现，则该返回-1

#### 布尔类型
+ 布尔型值只有两个：true和false，分别表示真和假
#### undefined是什么
+ 一个没有被赋值的变量的默认值是undefined，而undefined的类型也是undefined
+ 即：undefined又是值，又是一种类型，这种类型只有它自己一个值
##### 变量声明提升的情况
+ 在变量声明提升时，变量的值也是undefined
```
console.log(a);//undefined
console.log(typeof a);//undefined
var a=10;//变量声明提升，只提升变量声明不提升值
```
#### null类型
+ null表示"空"，它是"空对象"
+ 当我们需要将对象销毁、数组销毁或者删除事件监听时，通常将它们设置为null
```
box.onclick =null;
```
+ 使用typeof检测null值，结果是object，注意
+ 类型和typeof检测结果并不是一一对应
#### 数据类型转换
+ 其他值转换数字 Number()
```
Number('123');//123
Number('123.4');//123.4
Number('123年');//NaN
Number('2e3');//2000
Number('');//0
Number(true);//1
Number(false);//0
Number(undefined);//NaN
Number(null);//0
```
+ parseInt()函数
    + parseInt()将自动截掉第一个非数字字符之后所有字符，不会进行四舍五入
```
parseInt('3.14');//3
parseInt('3.14是圆周率');//3
parseInt('圆周率是3.14');//NaN
parseInt('3.99');//3
```
+ parseFloat()函数
    + parseFloat()函数的功能是将字符串转为浮点数,不四舍五入
```
parseInt('3.14');//3.14
parseInt('3.14是圆周率');//3.14
parseInt('圆周率是3.14');//NaN
parseInt('3.99');//3.99
```
+ 其他值转换为字符串 String()函数
```
String(123);//'123'
String(123.4);//'123.4'
String(2e3);//'2000'
String(NaN);//'NaN'
String(Infinity);//'Infinity'
String(0xf);//'15'
//变为长得相同的字符串，科学计数法和非十进制都会转变为十进制
```
+ toString()方法
```
var a=6;
a.toString();
(6).toString();
```
+ 其他值转变为布尔值
    + Boolean()函数
```
Boolean(123);//true
Boolean(0);//false
Boolean(NaN);//false
Boolean(Infinity);//true
Boolean('');//false
Boolean('abc');//true
Boolean('false');//true
Boolean(undefined);//false
Boolean(null);//false


```


### 复杂数据类型