---
published: true
layout: post
title: nodejs的require模块及路径
categories: nodejs
tags: 
  - 工具
 
time: 2016.12.12 15:05:00
excerpt: 在nodejs中，模块大概可以分为核心模块和文件模块。

---

**在nodejs中，模块大概可以分为核心模块和文件模块。**
> 核心模块是被编译成二进制代码，引用的时候只需require表示符即可，如`require('net')`。


> 文件模块，则是指js文件、json文件或者是.node文件。
> 在引用文件模块的时候后要加上文件的路径：/.../.../xxx.js表示绝对路径、./xxx.js表示相对路径(同一文件夹下的xxx.js)，../表示上一级目录。如果既不加/.../、../又不加./的话，则该模块要么是核心模块，要么是从一个node_modules文件夹加载。

对于加载模块时既没指出./ ../ /.../时，加载模块的搜索路径。如果'/home/ry/projects/foo.js' 中的文件调用了 `require('bar.js') `，node将在下面的位置进行搜索：
- /home/ry/projects/node_modules/bar.js
- /home/ry/node_modules/bar.js
- /home/node_modules/bar.js
- /node_modules/bar.js


文件夹作为模块：
首先在文件夹的根下建立package.json文件，它标识了一个主模块。一个package.json中的内容可能如下：
```
{ "name" : "some-library",  
"main" : "./lib/some-library.js" } 
```
如果这是在一个文件夹./some-library下，那么`require('./some-library')`时将试图加载./some-library/lib/some-library.js

如果在这个目录下没有package.json文件，node将试图从这个目录下加载index.js或index.node文件。

例如，如果上面没有package.json文件，那么`require('./some-library')`时，将试图加载下面的文件：
- ./some-library/index.js
- ./some-library/index.node


*本文转自：http://www.cnblogs.com/pigtail/archive/2013/01/14/2859929.html*