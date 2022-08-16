## this指向
#### 全局作用域中的this指向(window)
    ```
    console.log(this);//window
    ```
+ 一般函数（非箭头函数）中的this指向
    ```
    `use strict`;//在严格模式下
    function add(){
        console.log(this);
    }
    add();//undefined->window(非严格模式下)
    window.add();
    
    ```
    ```
     const calc = {
        add: add()
    };
    // calc.add();//指向calc对象
    const adder = calc.add;
    adder();//undefined->window(非严格模式下)
    ```
    ```

    document.onclick = function(){
        console.log(this);
    };//指向document
    ```

+  只有在函数调用的时候this指向才确定，不调用的时候，不知道指向谁,this指向和函数在哪儿调用没关系，只和谁在调用有关.构造函数中this指向实例化对象

#### 箭头函数中的this指向
+ 箭头函数没有自己的this
    ```
           const calc = {
            add: () =>{
                console.log(this);
            }
        };
        calc.add();//window
    ```

#### 不适合使用箭头函数的情况
+ 作为构造函数
+ 需要this指向调用对象的时候
+ 需要使用arguments的时候
