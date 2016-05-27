---
layout: wiki
title: 扩展：红外巡线
---

# {{ page.title }}

> 作者：Songyimiao

本章节为大伙讲解如何在MWbalanced 2.0上扩展舵机。

演示视频传送门：[我是视频](http://v.youku.com/v_show/id_XMTU3NjM1ODM4MA==.html)

先看原理图，如图1，MWbalanced控制板预留出红外模块接口。

![红外](/img/wiki/infrared-001.png)

图1

红外对检测距离是有要求的，一般为1-3cm。我们用螺丝和铜柱等，把红外模块固定在下层亚克力板上，然后再接好线。如图2。

![红外安装](/img/wiki/infrared-002.jpg)

图2

我们在APP 1.4上增加了“巡线启动”控制按钮，如图3。

![APP1.4](/img/wiki/infrared-003.png)

图3

把小车放好位置，然后连接APP，按一下“巡线启动”，小车就会自行巡线，停止按“停止运动”即可。
