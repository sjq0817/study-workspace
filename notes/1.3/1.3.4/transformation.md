## 旋转变形
+ 将transform属性的值设置为rotate(),即可实现旋转变形
```
transform: rotate(45deg);
/*旋转角度*/
```
+ 若角度为正，则顺时针方向旋转，否则逆时针方向旋转

#### transform-origin属性
+ 使用transform-origin属性设置自己的自定义变换原点

## 缩放变形
+ 将transform属性的值设置为scale(),即可实现缩放变形
```
transform:scale(3);
/*缩放倍数*/
```
+ 当数值小于1时，表示缩小元素，大于1表示放大元素

## 斜切变形
+ 将transform属性的值设置为skew(),即可实现斜切变形
```
transform: skew(10deg, 20deg);
/*x斜切角度 y斜切角度*/
```

## 位移变形
+ 将transform属性的值设置为translate(),即可实现位移变形
```
transform: translate(100px,200px);
/*向右移动  向下移动 */
```
+ 和相对定位非常像，位移变形也会“老家留坑”，“形影分离”

## 3D旋转
+ 将transform属性的值设置为rotateX()或者rotateY(),即可实现绕横轴、纵轴旋转
```
transform:rotateX(30deg);
/*后仰*/
transform:rotateY(30deg);
/*右仰*/
```
##### perspective属性
+ perspective属性用来定义透视强度，可以理解为“人眼到舞台的距离”，单位是px
+ 要有舞台再有演员

## 空间移动
+ 当元素进行3D旋转后，即可继续添加translateX()、translateY()、translateZ()属性让元素在空间进行移动
+ 一定要记住，空间移动要添加在3D旋转之后
```
transform: rotateX(30deg) translateX(30px) translateY(30px) translateZ(100px);
/*左右 前后 上下*/
```
##### 
![image](https://img2.baidu.com/it/u=685204014,641452586&fm=26&fmt=auto&gp=0.jpg)
