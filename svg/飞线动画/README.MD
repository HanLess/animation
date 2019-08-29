#### 二维贝塞尔曲线

二维贝塞尔曲线有三个点：起点、控制点、终点，在 svg 中

```
<path
  d="M 10, 30 Q 100, 200 500 600"
></path>
```

M 是起点；Q 的两个坐标分别是控制点和终点

#### 飞线的例子

需要不断绘制贝塞尔曲线，知道完成；既然曲线是动态绘制的，现在已知起点（M），终点是动态变化的，是所绘制曲线的末端，也是已知的；所以只要找到每一段贝塞尔曲线的控制点，就可以实时绘制出此时的曲线

思路如下：

<img src="https://raw.githubusercontent.com/HanLess/animation/master/svg/img/640.webp" />

起点不变 P0；终点是实时的点 P02；控制点是实时的点 P01。所以我们要求的就是每一个阶段的 P01。

<img src="https://raw.githubusercontent.com/HanLess/animation/master/svg/img/%E5%85%AC%E5%BC%8F.webp" />

起点（M）已知

曲线末端通过 getPointAtLength 方法得到，算出 P01 即可

#### 蒙板

绘制出的曲线是一条完整的实线，要想得到飞线的效果，需要用蒙板

```
<mask id="Mask">
    <circle id="m-circle" cx=x cy=y r="150" fill="url(#grad)"  />
</mask>
```

蒙板覆盖的地方才会显示，其他地方会隐藏，所以蒙板跟着曲线末端移动就可以，即实时更新 cx , cy 即可，值是曲线末端，通过 getPointAtLength 得到
