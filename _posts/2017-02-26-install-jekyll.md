---
layout: default
---
# jekyll的windows安装
<br />
<br />
使用jekyll可以在自己的blog上传到github之前进行编辑预览。
如果英文比较厉害，可以直接去看下"https://pages.github.com/" ， 里面有详细的安装过程讲解~



![](http://i.imgur.com/5XxORlF.jpg)



---
<br />
<br />
### 安装过程：



1.确认电脑有安装python、ruby，如果没有，请先下载安装它们



![](http://i.imgur.com/KaJG92C.jpg)



2.安装jekyll:



`> gem install jekyll`



![](http://i.imgur.com/5LZFqO7.jpg)



3.在本地新建一个目录，然后cd到目录下指令新建一个站点:



`> jekyll new 你的blog名`



![](http://i.imgur.com/Q5nBXcR.jpg)



4.电脑进入目录，可以看到站点已生成



![](http://i.imgur.com/83ACAMH.jpg)



5.再CD到目录下面启动站点



`> jekyll serve`



![](http://i.imgur.com/0SXY6zY.jpg)



6.这时在浏览器栏输入“localhost:4000”就可以访问页面了



![](http://i.imgur.com/aN79CL7.jpg)



---



剩下的就靠自己去做改动吧



后记：
刚玩github不久，今天安装jekyll想到要把过程记下来，这里说一下对站点里面文件的了解
>##### _config.yml：用于保存配置。（jekyll会自动加载这些配置），里面的配置的东西有比如title，email等，也可以加入自定义的配置，以上配置在其他地方以\{\{site.配置名称\}\}的方式引用，>#后面是注释，如果.yml文件有改动，需要重新运行jekyll serve才会把配置生效
>##### _includes文件夹：存放可以重复利用的文件，可以被其他的文件包含（方法：\{　% include 文件名 %　\}）
>##### _layouts文件夹：存放模板文件（标签\{\{ content \}\}将content插入页面中）。
>##### _posts文件夹：存放实际的博客文章内容（文件名格式：年-月-日-标题.md或者html,日期不能超过今天），使用markdown语言。里面的html,head,body标签不是必须的，想以哪种模板打开本页面则头文件layout: 设置为_layouts文件夹里面的对应模板文件名称，比如layout: post,注意冒号后要有空格。要注意实体化字符,多个回车换一行，也可用\<br /\>。
>##### _site文件夹：存放最终生成的文件（其他的目录都会被拷贝到最终文件的目录下。所以css,images等目录都可以放在根目录下）。















