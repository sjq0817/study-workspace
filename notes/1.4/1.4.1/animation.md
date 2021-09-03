## 动画的定义
+ 可以使用@keyframes来定义动画，keyframes表示“关键帧”，在项目上线前，要补上@-webkit-这样的私有前缀
```
@keyframes r {
    from {
        trnasform: rotate(0);
    }
    to {
        transform: rotate(360deg);
    }
}
/*
@keyframes 定义动画  
r 动画名字
from 起始状态
to  结束状态
*/
```
## 动画的调用
+ 定义动画之后，就可以使用animation属性调用动画
```
animation: r 1s linear 0s;
/*  动画名字 总时长 缓动效果 延迟*/
```
#### 动画的执行次数
+ 第五个参数就是动画的执行次数
```
animation: r 1s linear 0s 3;
/*                         次数*/
```
+ 如果想永远执行可以写infinite
```
animation: r 1s linear 0s infinite;
```
#### alternate 和 forwards
+ 如果想让动画的第2、4、6....（偶数次）自动逆向执行，那么要加上alternate参数即可
```
animation: movelr 2s linear 0s infinite alternate;
```
+ 如果想让动画停止在最后结束状态，那么要加上forwards
```
animation: changeToCircle 1s linear 0s forwards;
```
#### 多关键帧动画
```
@keyframes changeColor {
    0% {
        background-color: red;
    }
    20% {
        background-color: yellow;
    }
    40% {
        background-color: blue;
    }
    60% {
        background-color: green;
    }
    80% {
        background-color: purple;
    }
    100% {
        background-color: orange;
    }
}
```