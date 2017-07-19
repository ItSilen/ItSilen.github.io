---
published: true
layout: post
title: bootstrap简介
categories: bootstrap
tags: 
  - 前端框架
time: 2016.12.05 14:46:53
excerpt: bootstrap是Twitter公司开发的基于html,css,JavaScript的前端框架

---

![](http://i.imgur.com/u5yLdwV.png)

# bootstrap #
> 是Twitter公司开发的基于html,css,JavaScript的前端框架，
> 为实现web应用程序快速开发提供的一套前端工具包，
> 使用响应式布局，
> 移动设备优先。

**bootstrap的特性**

- 响应式设计
- 栅格布局
- 完整的类库
- jquery插件
- 不同的使用场景

**移动设备优先**

在 Bootstrap 2 中，我们对框架中的某些关键部分增加了对移动设备友好的样式。而在 Bootstrap 3 中，我们重写了整个框架，使其一开始就是对移动设备友好的。这次不是简单的增加一些可选的针对移动设备的样式，而是直接融合进了框架的内核中。也就是说，Bootstrap 是移动设备优先的。针对移动设备的样式融合进了框架的每个角落，而不是增加一个额外的文件。

为了确保适当的绘制和触屏缩放，需要在 <head> 之中添加 viewport 元数据标签。
```
<meta name="viewport" content="width=device-width, initial-scale=1">
```


**引用**

![](http://i.imgur.com/2FqEMjU.png)

## bootstrap全局样式 ##
包括：
- 栅格系统
- 排版
- 代码
- 表格
- 表单
- 按钮
- 图片
- 辅助类
- 响应式工具
- 使用 Less
- 使用 Sass


### 排版 ###

**标题**

HTML 中的所有标题标签，`<h1>` 到 `<h6>` 均可使用。另外，还提供了` .h1` 到` .h6` 类，为的是给内联（inline）属性的文本赋予标题的样式。
在标题内还可以包含 `<small>` 标签或赋予` .small` 类的元素，可以用来标记副标题。

**对齐**

通过文本对齐类，可以简单方便的将文字重新对齐。
```
<p class="text-left">Left aligned text.</p>
<p class="text-center">Center aligned text.</p>
<p class="text-right">Right aligned text.</p>
<p class="text-justify">Justified text.</p>
<p class="text-nowrap">No wrap text.</p>
```

### 栅格系统 ###

**bootstrap可以响应式页面，栅格系统适配不同的硬件**

![](http://i.imgur.com/y6zyMu8.png)

![](http://i.imgur.com/Drucfpo.png)

![](http://i.imgur.com/J1r5eXx.png)

## 组件 ##

包括：

- Glyphicons 字体图标
- 下拉菜单
- 按钮组
- 按钮式下拉菜单
- 输入框组
- 导航
- 导航条
- 路径导航
- 分页
- 标签
- 徽章
- 巨幕
- 页头
- 缩略图
- 警告框
- 进度条
- 媒体对象
- 列表组
- 面板
- 具有响应式特性的嵌入内容
- Well

### 字体图标 ###

特点：
- 体积小便于加载
- 无需重复设计
- 方便引用


![](http://i.imgur.com/O7GvhNG.png)

### 下拉菜单 ###

用于显示链接列表的可切换、有上下文的菜单。下拉菜单的 JavaScript 插件让它具有了交互性。
将下拉菜单触发器和下拉菜单都包裹在 .dropdown 里，或者另一个声明了 position: relative; 的元素。然后加入组成菜单的 HTML 代码。

```
<div class="dropdown">
  <button class="btn btn-default dropdown-toggle" type="button" id="dropdownMenu1" data-toggle="dropdown" aria-haspopup="true" aria-expanded="true">
    Dropdown
    <span class="caret"></span>
  </button>
  <ul class="dropdown-menu" aria-labelledby="dropdownMenu1">
    <li><a href="#">Action</a></li>
    <li><a href="#">Another action</a></li>
    <li><a href="#">Something else here</a></li>
    <li role="separator" class="divider"></li>
    <li><a href="#">Separated link</a></li>
  </ul>
</div>
```


### 分页 ###

为您的网站或应用提供带有展示页码的分页组件，或者可以使用简单的翻页组件。

默认分页
受 Rdio 的启发，我们提供了这个简单的分页组件，用在应用或搜索结果中超级棒。组件中的每个部分都很大，优点是容易点击、易缩放、点击区域大。
```
<nav aria-label="Page navigation">
  <ul class="pagination">
    <li>
      <a href="#" aria-label="Previous">
        <span aria-hidden="true">&laquo;</span>
      </a>
    </li>
    <li><a href="#">1</a></li>
    <li><a href="#">2</a></li>
    <li><a href="#">3</a></li>
    <li><a href="#">4</a></li>
    <li><a href="#">5</a></li>
    <li>
      <a href="#" aria-label="Next">
        <span aria-hidden="true">&raquo;</span>
      </a>
    </li>
  </ul>
</nav>
```

## JavaScript 插件 ##

jQuery 插件为 Bootstrap 的组件赋予了“生命”。可以简单地一次性引入所有插件，或者逐个引入到你的页面中。
插件的引用，jquery引用之后再使用bootstrap，有先后顺序

- 过渡效果
- 模态框
- 下拉菜单
- 滚动监听
- 标签页
- 工具提示
- 弹出框
- 警告框
- 按钮
- Collapse
- Carousel
- Affix

### 过渡效果 transition.js ###

关于过渡效果
对于简单的过渡效果，只需将 transition.js 和其它 JS 文件一起引入即可。如果你使用的是编译（或压缩）版的 bootstrap.js 文件，就无需再单独将其引入了。

包含的内容
Transition.js 是针对 transitionEnd 事件的一个基本辅助工具，也是对 CSS 过渡效果的模拟。它被其它插件用来检测当前浏览器对是否支持 CSS 的过渡效果。


### 滚动监听 scrollspy.js ###

导航条实例
滚动监听插件是用来根据滚动条所处的位置来自动更新导航项的。如下所示，滚动导航条下面的区域并关注导航项的变化。下拉菜单中的条目也会自动高亮显示。

依赖 Bootstrap 的导航组件
滚动监听插件依赖 Bootstrap 的导航组件 用于高亮显示当前激活的链接

需要相对定位（relative positioning）
无论何种实现方式，滚动监听都需要被监听的组件是 position: relative; 即相对定位方式。大多数时候是监听 <body> 元素。When scrollspying on elements other than the <body>, be sure to have a height set and overflow-y: scroll; applied.

通过 data 属性调用
```
body {
  position: relative;
}

<body data-spy="scroll" data-target="#navbar-example">
  ...
  <div id="navbar-example">
    <ul class="nav nav-tabs" role="tablist">
      ...
    </ul>
  </div>
  ...
</body>
```
通过 JavaScript 调用
在 CSS 中添加 `position: relative;` 之后，通过 JavaScript 代码启动滚动监听插件：

```
$('body').scrollspy({ target: '#navbar-example' })
```


### 标签页 tab.js ###

使用

```
$('#myTabs a').click(function (e) {
  e.preventDefault()
  $(this).tab('show')
})
```
```
<div>

  <!-- Nav tabs -->
  <ul class="nav nav-tabs" role="tablist">
    <li role="presentation" class="active"><a href="#home" aria-controls="home" role="tab" data-toggle="tab">Home</a></li>
    <li role="presentation"><a href="#profile" aria-controls="profile" role="tab" data-toggle="tab">Profile</a></li>
    <li role="presentation"><a href="#messages" aria-controls="messages" role="tab" data-toggle="tab">Messages</a></li>
    <li role="presentation"><a href="#settings" aria-controls="settings" role="tab" data-toggle="tab">Settings</a></li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content">
    <div role="tabpanel" class="tab-pane active" id="home">...</div>
    <div role="tabpanel" class="tab-pane" id="profile">...</div>
    <div role="tabpanel" class="tab-pane" id="messages">...</div>
    <div role="tabpanel" class="tab-pane" id="settings">...</div>
  </div>

</div>
```

### 按钮 button.js ###

按钮的功能很丰富。通过控制按钮的状态或创建一组按钮并形成一些新的组件，例如工具条。

跨浏览器兼容性
在页面多次加载之间，Firefox 仍然保持表单控件的状态（禁用状态和选择状态）。一个解决办法是设置 autocomplete="off"。参见 Mozilla bug #654072。
```
<button type="button" id="myButton" data-loading-text="Loading..." class="btn btn-primary" autocomplete="off">
  Loading state
</button>

<script>
  $('#myButton').on('click', function () {
    var $btn = $(this).button('loading')
    // business logic...
    $btn.button('reset')
  })
</script>
```


----------

这里只是对Bootstrap进行了大概的介绍，具体更多请到
**boostrap官网地址**
- 官方地址：http://getbootstrap.com
- 中文地址：www.bootcss.com




参考来源：imooc