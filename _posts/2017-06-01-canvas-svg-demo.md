---
published: true
layout: post
title: canvas-svg-demo
category: [canvas, svg, html5]
tags: 
  - canvas
  - svg
time: 2017.06.01 20:20:23
excerpt: 一个canvas时钟，canvas系列帧动画，通过imageData转换图像，svg制作的一个海上灯塔

---

演示地址：https://itsilen.github.io/canvas-svg-demo

一个canvas时钟，利用了canvas的几个基本api,如`fill, stroke ,save, restore, rotate`

![canvas时钟](http://i.imgur.com/QnkyNh7.png)


鼠标移到图片上面时，产生星星一闪一闪的系列帧动画，为了更好的性能，使用`requestAnimationFrame`循环动画

![闪闪的星星](http://i.imgur.com/y8qmW0u.png)

利用canvas的`getImageData， putImageData` api方法，制作图片的如反色，模糊，马赛克效果等等。

![](http://i.imgur.com/nPeHRl5.jpg)

svg制作的分散星星，一轮弯月，还有旋转灯塔
月亮的月牙效果利用了蒙板`mask`
旋转效果使用的是`animateTransform`

![](http://i.imgur.com/UZuDreO.png)

参考来源：imooc