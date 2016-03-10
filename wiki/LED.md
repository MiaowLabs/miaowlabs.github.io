---
layout: wiki
title: LED指示灯实验
---

# {{ page.title }}

> 作者：Songyimiao

在学会建立工程之后，我们就可以学习一个简单的实验：点亮LED指示灯。

MWbalancedSTC15的控制板上有四颗LED指示灯，其中一颗是蓝牙状态指示灯，一颗是USB插拔工作状态指示灯，另外两颗才是我们能自定义的LED指示灯。如下图。

![](/img/wiki/led-01.png)

![](/img/wiki/led-02.png)

然后我们在IOConfig.h里面定义好LED对应的引脚。如下图。

![](/img/wiki/led-03.png)

接着，初始化GPIO引脚，设置成“准双向”。如下图。可以不把所有引脚都初始化，只把LED用到的引脚初始化就可以了。

![](/img/wiki/led-04.png)

然后，在主函数里将两个LED灯设置成0.5秒闪烁一次。如下图。

![](/img/wiki/led-05.png)

就这样，大功告成。我们可以看到控制板上的LED在闪烁。

![](/img/wiki/led-06.gif)

LED指示灯实验代码传送门：（这几天整理下就上传）

