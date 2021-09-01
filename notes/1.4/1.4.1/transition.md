## transition过渡
+ transition过渡属性是CSS3浓墨重彩的特性，过渡可以为一个元素在不同样式之间变化自动添加“补间动画”
+ 定义开始状态，定义结束状态，自动添加补间动画
+ 过渡从IE10开始兼容，移动端兼容良好
+ 动画更细腻，内存开销小
+ transition属性有4个属性
```
transition: width 1s linear 0s;
/* 什么属性要过渡 动画时长 变化速度曲线 延迟时间 */
```
#### 哪些属性可以参与过渡
+ 所有数值类型的属性，都可以参与过渡，比如width、height、left、top、border-radius
+ 背景颜色和文字颜色都可以被过渡
+ 所有变形(包括2D和3D)都能被过渡


##### all
+ 如果要所有属性都参与过渡，可以写all(会引发效率问题)
```
transition: all 1s linear 0s;
```

###### 过渡的四个小属性

属性|意义
-|-
transition-property|哪些属性要过渡
transition-duration|动画时间
transition-timing-function|动画变化曲线
transition-delay|延迟时间

### 缓动参数
+ transition的第三个参数就是缓动参数，也是变化速度曲线
+ 常见缓动参数，ease两头慢中间快、linear匀速、ease-in开头慢后面越来越快、ease-out开头中间快结尾慢、ease-in-out两头慢中间快比ease更慢更平缓

##### 贝塞尔曲线
+ 网站 https://cubic-bezier.com/ 可以生成贝塞尔曲线，可以自定义动画缓动参数
```
transition: width 1s cubic-bezier(0.1,0.7,1.0,0.1) 0s;
```