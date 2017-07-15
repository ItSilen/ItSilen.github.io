---
published: true
layout: post
title: canvas-Wordpad写字板
category: [canvas,jquery]
tags: 
  - jquery
  - canvas
time: 2017.06.03 12:04:00
excerpt: 利用canvas技术与jquery制作的一个简单写字板。

---
利用canvas技术与jquery制作的一个简单写字板。

**在写字板写好后如果觉得效果满意，可以右键以png图片的形式保存下来**

地址：https://itsilen.github.io/canvas-Wordpad/ 或者扫二维码

![wordpad](http://i.imgur.com/wzWyGBU.png)


----------

背景
![背景](http://i.imgur.com/CT3mk87.png) 

----------

来一首放浪不羁的小学生字体

 ![床前明月光](http://i.imgur.com/PWNzGmB.png)![疑是地上霜，举头望明月](http://i.imgur.com/DxXADME.png) 

还可以调整线条粗细和颜色

 ![低头思故乡](http://i.imgur.com/90STrk7.png)![低头吃香菇](http://i.imgur.com/l8fOQsl.png)

----------


**这个作品的核心逻辑是onmousemove**。

> 按住鼠标左键并且移动鼠标的时候，onmousemove每隔一段时间就会执行一次，那么每执行的时候只要跟上一次鼠标所在的位置的点之间画直线就可以了.

粗线条引发的问题,把lineWidth设置大点，会很不平滑.
> 用lineCap=”round”,线条就平滑了，
> 然后也设置lineJoin=”round”，线条的过渡衔接会更加自然，整体会更加平滑。


> 鼠标或者手指在移动时线条的粗细是由运笔速度决定的，速度越小,线宽linewidth就越大，速度越大，LineWidth越小，看起来就越细。

但是这样线条非常的不平滑

> 平滑这个问题在我们制作游戏或者处理动画的时候会经常遇到，处理方法通常都是一致的，
> 也就是说要使用之前的信息来进行过渡，


> 这里我们的平滑方式包括决定笔画粗细的算法可以更加复杂得到更加逼真的方式。

> 在这里我们只是使用线性查值的方式来计算笔画的粗细，resultLineWidth = maxLineWidth - (v - minStrokeV) / (maxStrokeV - minStrokeV) * (maxLineWidth - minLineWidth);所以这个效果仍然不够满意，但是更复杂的方法就对数学的要求太高了，不是这里的重点。


怎样更好的适配移动端的屏幕

> 一个非常重要的概念，那就是在html的头部分需要写一个叫做viewport
> 的元信息。将指定我们的应用程序在不同的屏幕下具体的显示效果有什么，
> 
> 语法
> meta是一个元信息，name = “viewport”,关键在content部分，包含很多项，通常设置这六项就可以了，
> width,height，屏幕尺寸，可以设置固定的像素值，也可以使用device-width,也就是当前设备的宽高
> initial-scale，初始的伸缩量，也就是初始是否要缩放效果，通常是1.0,
> 最小最大缩放量，通常是不允许缩放，所以也是1.0
> 是否运行用户缩放，no.


使用到的屏幕触控响应事件

> touch事件
> 有三种
> 
> touchstart
> touchmove
> touchend










