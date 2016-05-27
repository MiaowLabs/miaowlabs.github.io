---
layout: wiki
title: 扩展：舵机
---

# {{ page.title }}

> 作者：Songyimiao

本章节为大伙讲解如何在MWbalanced 2.0上扩展舵机。

演示视频传送门：[我是视频](http://v.youku.com/v_show/id_XMTU3NjM1ODM4MA==.html)

先看原理图，如图1，MWbalanced控制板预留出两路PWM接口(舵机)，引脚兼容市面上常见的角度或速度舵机。

![舵机](/img/wiki/servo-001.png)

图1

可以用扎带或胶布或胶水等，把舵机固定在上层亚克力板上，然后再接好线。如图2。

![舵机安装](/img/wiki/servo-002.jpg)

图2

我们在APP 1.4上增加了舵机控制按钮，如图3。

![APP1.4](/img/wiki/servo-003.png)

如此一来，遥控舵机也是很方便啦。
