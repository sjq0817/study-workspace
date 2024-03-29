## 数组
+ 数组（Array），顾名思义，用来存储一组相关的值，从而方便进行求和、计算平均数、逐项遍历操作
    ```
    var scoreArr = [96,97,76,87];
    ```
+ 每种高级编程语言中都有数组，它是非常重要的一种数据结构


### 定义数组
+ 使用[]
    ```
    var arr = ['A','B','C','D'];
    ```
+ new
    ```
    var arr = new Array('A','B','C','D');
    ```
+ 直接定义数组长度,但这4项都是undefined
    ```
    var arr = new Array(4);
    ```
### 访问数组项
+ 数组每一项都有下标，下标从0开始
    ```
    var arr = ['A','B','C','D'];
                0   1   2   3
    ```
+ 可以使用方括号中书写下标的形式，访问数组的任一项
    ```
    console.log(arr[0]);//A
    console.log(arr[1]);//B
    console.log(arr[2]);//C
    console.log(arr[3]);//D
    ```
+ JavaScript规定，访问数组中不存在的项会返回undefined，不会报错
    ```
    var arr = ['A','B','C','D'];
    console.log(arr[4]);//undefined
    ```
#### 数组的长度
+ 数组的length属性表示它的长度
    ```
    var arr = ['A','B','C','D'];
    console.log(arr.length);//4
    
    ```
+ 数组最后一项的下标是数组的长度减1

#### 更改数组项
+ 数组并不是只读的，我们可以修改它其中任何项的值
    ```
    var arr = [2,6,7,3];
    arr[1]++;
    arr[2] = 0;
    console.log(arr);//[2,7,0,3]
    ```
+ 如果更改的数组项超过了length-1，则会创造这项
    ```
    var arr = [2,6,7,3];
    arr[6] = 4;
    console.log(arr);
    //[2,6,7,3,empty × 2,4]

    ```

#### 数组的遍历
+ 数组的最大的优点就是方便遍历
    ```
    var arr = ['A','B','C','D'];
    for (var i = 0; i < arr.length; i++) {
        console.log(arr[i]);
    }
    ```

#### 数组类型的检测
+ 数组用typeof检测结果是object
+ Array.isArray()方法可以用来检测数组
+ “鸭式辨型”检测方法


## 数组的常用方法
+ 数组的头尾操作方法

 方法|功能
 -|-
 push()|在尾部插入新项
 pop()|在尾部删除
 unshift()|在头部插入新项
 shift()|在头部删除

##### push()方法
+ push()方法用来在数组末尾推入新项，参数就是要推入的项
+ 如果要推入多项，可以用逗号隔开
+ 调用push()方法后，数组会立即改变，不需要赋值
    ```
    var arr = [11,22,33,44];
    arr.push(55);
    ```

##### pop()方法
+ 与push()方法相反，pop()方法用来删除数组中的最后一项
+ pop()方法不仅会删除数组末项，而且会返回被删除的项

##### unshift()方法
+ unshift()方法用来在数组头尾插入新项，参数就是要插入的项
+ 如果要插入多项，可以用逗号隔开
+ 调用unshift()方法后，数组会立即改变，不需要赋值

##### shift()方法
+ 与unshift()相反,shift()方法用来删除数组中下标为0的项
+ shift()方法不仅会删除数组首项，而且会返回被删除的项

##### splice()方法
+ splice()方法用于替换数组中的指定项
    ```
    var arr = ['A','B','C','D','E','F'];
    arr.splice(3,2,'X','Y','Z');
    console.log(arr);
    //['A','B','C','X','Y','Z','F']
    ```

+ splice()方法可以用于在指定位置之前插入新项
    ```
    var arr = ['A','B','C','D','E','F'];
    arr.splice(3,0,'X','Y','Z');
    console.log(arr);
    //['A','B','C','X','Y','Z','D','E','F']
    ```
+ splice()方法可以用于删除指定项
    ```
    var arr = ['A','B','C','D','E','F'];
    arr.splice(3,3);
    console.log(arr);
    //['A','B','C']
    ```
+ splice()方法会以数组的形式返回被删除的项

##### slice()方法
+ slice()方法用于得到子数组，类似于字符串的slice()方法
+ slice(a,b)截取的子数组从下标为a的项开始，到下标为b（但不包括下标为b的项）结束
+ slice(a,b)方法不会更改原有数组
+ slice()如果不提供第二个参数，则表示从指定项开始，提取所有后续所有项作为子数组

##### join()方法和split()方法
+ 数组的join()方法可以使数组转为字符串；字符串的split()方法可以使字符串转为数组。
    ```
        ---> join()--->
    数组————————————————字符串
        <---split()<----
    ```

+ join()的参数表示以什么字符作为连接符，如果留空则默认以逗号分隔，如同调用toString()方法
+ split()的参数表示以什么字符拆分字符串，一般不能留空

```
[1,2,3,4].join();
//"1,2,3,4"
[1,2,3,4].toString();
//"1,2,3,4"
[1,2,3,4].join('-');
//"1-2-3-4"
'abcdef'.split('');
{"a","b","c","d","e","f"}
```

##### concat()方法
+ concat()方法可以合并连结多个数组
    ```
    var arr1 = [1,2,3,4];
    var arr2 = [5,6,7,8];
    var arr3 = [9,10,11];
    var arr = arr1.concat(arr2 , arr3);
    console.log(arr);
    //[1,2,3,4,5,6,7,8,9,10,11]
    ```
+ concat()方法不会改变原数组

##### reverse()方法
+ reverse()方法用来将一个数组中的全部项顺序置反
    ```
    var arr = ["A","B","C","D"];
    arr.reverse();
    console.log(arr);
    //["D","C","B","A"]
    ```

##### indexOf()方法和includes()方法
+ indexOf()方法的功能是搜索数组中的元素，并返回它所在的位置，如果元素不存在，则返回-1
+ includes()方法的功能是判断一个数组是否包含一个指定的值，返回布尔值
+ 包含类型即===

### 遍历相关算法
+ 
## 冒泡排序
+ 冒泡排序是一个著名的排序算法，也是在面试时爱考
+ 冒泡排序的核心思路是一趟一趟地进行多次项的两两比较，每次都会将最小的元素排好位置，如同水中的气泡上浮一样
+ n个数字，共需要比较n-1趟，比较次数为n（n-1）/2次


## 二维数组
+ 以数组作为数组元素的数组，即“数组的数组”
+ 二维数组可以看做是矩阵
## 基本类型值和引用类型值
#### 基本类型
+ number boolean string undefined null
#### 引用类型
+ array object function regexp
#### 相等判断时的区别
+ 基本类型进行相等判断时，会比较值是否相等
+ 引用类型进行相等判断时，会比较址是否相等，也就是说它会比较是否为内存中的同一个东西
### 深克隆和浅克隆
+ 浅克隆：只克隆数组的第一层，如果是多维数组，或者数组中的项是其他引用类型值，则不克隆其他层
+ 深克隆：克隆数组的所有层，要使用递归技术