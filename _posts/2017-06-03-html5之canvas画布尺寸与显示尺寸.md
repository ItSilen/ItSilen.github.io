---
published: true
layout: post
title: html5之canvas画布尺寸与显示尺寸
categories: [html5, canvas]
tags: 
  - 图形
 
time: 2016.06.3 15:24:00
excerpt: canvas是一张画布，画布本身有一个尺寸，绘制各种图形都是按照画布尺寸去画，而画布最终会显示到页面中，像一张图片那样，我们可以通过css设置其大小，这就是显示尺寸，图像已经确定，此时是拉伸。

---

## 概要 ##
canvas是一张画布，画布本身有一个尺寸，绘制各种图形都是按照画布尺寸去画，而画布最终会显示到页面中，像一张图片那样，我们可以通过css设置其大小，这就是显示尺寸，图像已经确定，此时是拉伸。

很多人在初学Html5的canvas时都会遇到一个问题，css改变了canvas的尺寸后，本来是可以画出一个圆来，现在却是一个扁平的圆。

![](http://i.imgur.com/xDel3Px.png)

## 原因分析 ##
canvas相当于一张图片，它自身有个尺寸，是内容的尺寸，默认大小为：300px*150px，当我们使用css设置这个canvas大小为800px*600px时，看起来画布变成了800x600，其实它本身的内容还是300x150，也就是此时的内容将会被拉伸，这就是图像变形的原因。

## 解决方案 ##
JavaScript
使用元素属性来改变：
```
<canvas width=500 height=400></canvas>
 
对应的javascript是：
canvas=document.getElementsByTagName('canvas')[0];
canvas.width=500;
canvas.height=400;
```


*本文转自：http://baike.xsoftlab.net/view/724.html*