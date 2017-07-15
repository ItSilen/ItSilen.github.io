---
published: true
layout: post
title: 在python中使用sqlite的时候应注意防止注入攻击
category: python
tags: 
  - sql
time: 2016.08.19 14:19:00
excerpt: 在python的文档中有大概这样一段描述：在使用sql语句操纵数据库的时候，不应该直接将字符串连接起来作为sql语句进行查询，因为直接将外部传入的字符串代入到sql语句中就会产生sql注入的问题。

---
在python的文档中有大概这样一段描述：
在使用sql语句操纵数据库的时候，不应该直接将字符串连接起来作为sql语句进行查询，因为直接将外部传入的字符串代入到sql语句中就会产生sql注入的问题。
比如下面是一个错误的用法
```
symbol = &#39;IBM&#39;
c.execute("... where symbol = &#39;%s&#39;" % symbol)
```
#错误的用法，会带来sql注入
在实际使用的时候，应该使用数据库API提供的参数替代方法传递外部的参数。也就是常说的“一个萝卜一个坑”。把需要执行的sql参数作为数据库API的某个函数的参数传递进去，这样在API内部就做了对敏感字符的转义工作。
下面是正确的用法：
```
t = (symbol,)
c.execute(&#39;select * from stocks where symbol=?&#39;, t)
# Larger example
for t in [(&#39;2006-03-28&#39;, &#39;BUY&#39;, &#39;IBM&#39;, 1000, 45.00),
 (&#39;2006-04-05&#39;, &#39;BUY&#39;, &#39;MSOFT&#39;, 1000, 72.00), 
(&#39;2006-04-06&#39;, &#39;SELL&#39;, &#39;IBM&#39;, 500, 53.00), ]:
c.execute(&#39;insert into stocks values (?,?,?,?,?)&#39;, t)
```
在python中，这种语法的用法是：在sql语句的任意位置使用问号替代参数，然后把外部传递进来的参数放在一个数组中，然后把数组作为`cursor.execute()`方法的参数传递进去查询。

*本文转自：http://m.2cto.com/kf/201301/182047.html*