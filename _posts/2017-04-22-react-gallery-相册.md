---
published: true
layout: post
title: react-gallery-相册
category: react
tags: 
  - react
time: 2017.04.22 16:03:53
excerpt: React首次被提出是在2014年的f8大会上，f8是由facebook组织的一个年度的技术峰会，目标听众是从事web周边产品和服务的开发者及企业，之所以叫f8是因为fb内部编程马拉松是限制在8小时以内的，就看大家在8小时以内能做出哪些有意思的东西

---

这是一个用react写的相册，可以放几张美女的照片上去。

演示地址：https://itsilen.github.io/gallery-by-react/

![](http://i.imgur.com/FrCbgjR.png)


React组件的生命周期可分成三个状态：

> Mounting：已插入真实 DOM 
> 
> Updating：正在被重新渲染 
> 
> Unmounting：已移出真实 DOM

生命周期的钩子方法有：

> componentWillMount 在渲染前调用,在客户端也在服务端。


> componentDidMount : 在第一次渲染后调用，只在客户端。之后组件已经生成了对应的DOM结构，可以通过this.getDOMNode()来进行访问。 如果你想和其他JavaScript框架一起使用，可以在这个方法中调用setTimeout, setInterval或者发送AJAX请求等操作(防止异部操作阻塞UI)。


> componentWillReceiveProps 在组件接收到一个新的prop时被调用。这个方法在初始化render时不会被调用。


> shouldComponentUpdate 返回一个布尔值。在组件接收到新的props或者state时被调用。在初始化时或者使用forceUpdate时不被调用。 
可以在你确认不需要更新组件时使用。

> componentWillUpdate在组件接收到新的props或者state但还没有render时被调用。在初始化时不会被调用。

> componentDidUpdate 在组件完成更新后立即调用。在初始化时不会被调用。

> componentWillUnmount在组件从 DOM 中移除的时候立刻被调用。

用一张图表示

![Lifecycle](http://i.imgur.com/JcdtQLA.png)

需要了解构建站点的vcd原则，就是
- view视觉
- control控制
- data数据

获取元素各种宽度的区别

> scrollWidth:是对象的实际内容宽度，不包含滚动条等边线，会随对象中内容超过可视区域后变大。
> 
> clientWidth:是对象内容的可视区域宽度，不包含滚动条等边线，会随对象显示大小而变化。
> 
> offsetWidth：是对象整体的实际宽度，包含滚动条等边线，会随对象显示大小而变化。


我们舞台的布局，粗略分成5个部分
中心图片区域左侧右侧上侧下侧
首先需要从图片组里面挑一张出来放在中心区域。然后其他的图片在其他四个区域排布，
这里为了不对下侧控制组件造成 过多的干扰。只排布左上右区域，
那各个区域能够放置的位置怎么划分呢，非常简单，就是找极限条件，极限条件内的值就是我们的区域，蓝色区域就是我们的舞台，这里规定一个图片至少露出他的1/4

![分区](http://i.imgur.com/aRi5YWZ.png)

![分区](http://i.imgur.com/bqHFKe4.png)

**React的特性就是state变化了就会重新渲染，比如当使用this.setState就会触发重新渲染**

图片旋转rotate
为了旋转的好看，我们限制一下正负旋转角度最大的30度，也就是旋转0到30度之间的随机角度。

中间图片点击可以翻转
图片翻转有两个地方可以控制，一个是点击中间图片自身，一个是点击中心图片相关联的控制按钮

图片旋转和翻转都会有一个过渡效果tansition

Perspective景深
> 可以简单理解为用户和元素3d空间x轴y轴形成的平面，称为z平面，之间的沿z轴方向的垂直距离就是红线指出的这段距离，值越小用户与3d空间z平面距离越近视觉效果就更令人印象深刻，反之值越大用户与3d空间z平面的距离越远，视觉效果就很小了

我们在控制组件插入的是图片字体Icon font

> Icon font技术用字体文件去图代图片文件来展示图标
好处：Icon font的体积要比图片小得多，是矢量图形拉伸不变形颜色可自行更换，支持css3属性对文字的效果修饰，



参考来源：imooc, runoob
