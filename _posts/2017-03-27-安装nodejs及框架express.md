---
published: true
layout: post
title: 安装nodejs及框架express
categories: [nodejs, express]
tags: 
  - 工具
  - 后端框架
 
time: 2016.03.27 11:44:00
excerpt: 安装步骤简单比较简单，所以在这里不会详细讲解每一步，只把安装过程中的问题解决了。

---

## 工具/原料 ##
- nodejs
- 框架express

## 方法/步骤 ##
1.从node官网下载安装文件，官网地址：http://nodejs.org/
 
![](http://i.imgur.com/21Ju4aG.png)

2.这个安装程序也很常规，顺序点击下一步就可以，或者做一些简单的选择，无需多说，只需强调一点，其中一步如图所示:Add To Path一定要选上。这个的作用简单说就是，在windows命令行添加node相关命令，详细请自行百度。

![](http://i.imgur.com/WaLY6B8.png)
 

3.我们非常愉快地把node安装完成，然后安装express，express是node官方唯一推荐的一个web框架，提供很多基础方便的功能。
4.在命令行中执行 `npm install -g express`等待下载并且自动完成安装。测试express完成安装的一个方法就是查看其版本号，执行命令 `express -V`正常情况下回输出版本号如图，但有遇到不正常情况的，会提示“express不是内部或外部命令”，这样问题就来了，这是什么原因呢？
 
![](http://i.imgur.com/L4vWc7M.png)

	
有两种可能：①在第二步安装node是没有添加环境变量，这种情况把node添加的环境变量即可解决。②express 4.x版本中将命令工具分出来了，需要再安装一个命令工具，执行命令`npm install -g express-generator`完成后再测试就可以了。

*本文转自：http://jingyan.baidu.com/article/456c463b60fb380a583144a9.html*
