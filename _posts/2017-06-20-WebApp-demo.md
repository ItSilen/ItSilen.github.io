---
published: true
layout: post
title: webapp-demo
categories: [zeptojs, WebApp,html5, canvas,JavaScript, photoshop]
tags: 
  - 相册
  - 贺卡
time: 2017.06.20 11:39:23
excerpt: 用zepto制作的在线相册。一个新年贺卡demo

---
由于是针对移动端webapp，最好是用手机浏览页面。
演示地址：https://itsilen.github.io/webapp-demo/

二维码

![webapp demo](http://i.imgur.com/YsQ0AFa.png)

# 在线相册 #
使用的是**zepto.js**

## zepto.js ##

> 根据[zepto官网](http://zeptojs.com)的定义，它是一个简化的不能再简化的js库，是为现代浏览器而生的。
有一句很精辟的话，就是如果你会用**jquery**，那么就会用**zepto** 

![zepto](http://i.imgur.com/OWuzzpp.png)

另外触屏的动作要使用**touch.js**，是**zepto**额外的module，需要单独安装。

> 原生的touch事件就是touchstart touchend touchmove
但是这些事件并不能代表人类真实的对手机行为，
touch.js封装了一些事件，比如手按一下屏幕再轻抬叫tap事件，
左滑右滑swipeLeft, swipeRight
长按longtap


点击相片展示，相片切换等有个动画效果，使用下载第三方的css3框架**animate.css**。

> 使用的时候必须要有个class叫做animated, 
然后要什么效果只需要加个名称就可以了，使用起来非常方便。

使用**canvas**代替**image**标签
> **canvas**能够触发物理上的**gpu**渲染，达到优化的目的。

关于大图显示效果

> 如果是横图，就尽量让它的宽度占满屏幕，上下留padding,
如果是竖图，就尽量让它的高度占满屏幕，左右留padding,

效果

![album](http://i.imgur.com/uQfp3Yv.png)

![large](http://i.imgur.com/cdtMxsa.png)

# 新年贺卡 #

对开发流程有一个基本的了解

> 切图，重构，
当然有时候先搭重构，先搭框架，然后再把图切出来放进去，
或者先把特效这一块的，类库啊，用什么框架框架这些先把环境搭好，这些都是可以的，
这块怎么灵活控制呢，是开发过程中能够慢慢掌握的


分开了三个页面，点击第一个页面会依次显示剩余的页面，为了页面跳转不会显得突然，中间有个过渡的动画，可以有更好的浏览体验。

里面用到的几个图片参考资源稍微用**photoshop**修改了一下。

![ps](http://i.imgur.com/bruEfF1.png)

背景音乐播放控制使用`audio`的`play`与`pause`方法。

**zepto**相当于移动端的**jquery**，但是会多服务器请求，这里用原生**js**代替。

大体过程无非就是html,body设置`height: 100%;overflow:hidden`,这样只显示一屏页面。
接着写好三个高度100%的页面，通过display来控制页面的显示隐藏，达到页面切换的效果。
css animation与@keyframes关键帧定义页面切换的动画，还有右上角音乐播放动画的控制等。

效果

![page1](http://i.imgur.com/ZR4BDX3.png)

![page2](http://i.imgur.com/BRCpzFc.png)

![page3](http://i.imgur.com/Y1yMjb2.png)


*参考来源：imooc*