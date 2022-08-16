## ES6
+ ES6就是ECMAScript这门语言语言的第六代标准
+ 6是版本号

## ECMA
+ 欧洲计算机制造协会
+ 标准化组织
+ ECMAScript是由ECMA这个标准化组织指定的一个语言标准


#### 具体是什么
+ 语法+API
#### 命名方式
+ ES6 VS ES2015

## ES与JavaScript的关系
+ JavaScript（浏览器端）= ECMAScript（语法+API）+ DOM + BOM

### ES6的兼容性
+ 主流浏览器的最新版本几乎全部支持ES6
+ IE老版本等不支持的浏览器，可以用Babel转码

## let const
### let const是什么
+ 声明变量或声明常量
+ var声明变量
+ let代替var，声明变量
+ const声明常量（constant的缩写）
### 用法
+ ```let age = 18;const sex = 'male';```
### 变量和常量的区别
+ let声明的就是变量，初始化后，变量可以重新赋值
+ const声明的就是常量，初始化后，常量不可以重新赋值
#### 为什么需要const
+ 一旦初始化不需要改变的值而诞生
+ 在不重新赋值的情况下修改常量值
+ 
```
const person = {username:'Alex'};
person.username = 'zhangsan';

```

#### const的注意事项
+ 使用const声明常量，一旦声明，就必须立即初始化，不能留到以后赋值
+ const声明的常量，允许在不重新赋值的情况下修改它的值



### 什么时候用const，什么时候用let
+ 不知道用什么用的时候就用const，防止在无意识的情况下改变值而不报错的情况
### let const与 var的区别
#### 重复声明
+ 已经存在的变量或常量，又声明了一遍
+ var允许重复声明，let const不允许

#### 变量提升
+ var会提升变量到当前作用域的顶部
+ let const 不存在变量提升
+ 养成良好的编程习惯，对于所有的变量或常量，做到先声明后使用

#### 暂时性死区
+ 只要作用域内存在let const，它们所声明的变量或常量就自动”绑定“这个区域不再受到外部作用域的影响

#### window对象的属性和方法
+ 全局作用域中，var声明的变量，通过function声明的函数会自动变成window对象的属性或方法
+ let const不会

#### 块级作用域
+ var 没有块级作用域
+ 

    ## 作用域链
    + 由内到外（内层作用域到外层作用域到全局作用域）不可由外到内
    + 有哪些作用域
        + {}、for(){}  while(){}  do{}while() if(){} switch(){}
        + 只有和let或者const相结合才会产生作用域

### let和const的应用