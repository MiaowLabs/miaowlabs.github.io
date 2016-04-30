---
layout: wiki
title: 通过USB烧写固件
---

# {{ page.title }}

> 作者：Songyimiao

注：本文适用于MWbalanced2.0。

烧写固件所需的东西：

* Micro-USB数据线；
* STC-ISP烧录工具；

MWbalanced2.0带有一颗USB-TTL芯片CP2102，所以可以直接通过USB接口下载或更新固件。

MWbalanced2.0使用的是外部晶振@20M，而且使用了STC15单片机内部复位电路，所以在烧写固件时，要先对STC-ISP做以下设置，再烧写操作，如图1所示。

![](/img/wiki/stc-isp-download.png)

图1

烧录成功后，STC-ISP会有操作成功提示。如图2所示。

![](/img/wiki/stc-isp-download-success.png)