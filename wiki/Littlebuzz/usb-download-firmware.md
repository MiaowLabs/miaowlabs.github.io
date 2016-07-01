---
layout: wiki
title: 通过USB烧写固件
---

# {{ page.title }}

> 作者：喵大

注：本文适用于Littlebuzz微型四轴飞行器。

烧写固件所需的东西：

* Micro-USB数据线；
* STC-ISP烧录工具；
* 最新固件

Littlebuzz带有一颗USB-Serial芯片CP2102，可以直接通过USB端口下载、更新固件。

Littlebuzz使用的是STC15**内部IRC时钟**@20M，而且使用STC15内部复位电路，所以在烧写固件时，要先对STC-ISP做以下设置，再烧写操作，如图1所示。

![](http://miaowlabs.com/img/wiki/littlebuzz/01.png)

图1

烧录成功后，STC-ISP会有操作成功提示。
