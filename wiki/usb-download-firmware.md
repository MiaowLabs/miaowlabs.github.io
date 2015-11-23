---
layout: wiki
title: 通过USB烧写固件
---

# {{ page.title }}

> 作者：Songyimiao

烧写固件所需的东西：

* Micro-USB数据线；
* STC-ISP烧录工具；

MWbalanced控制板带有一颗USB-TTL芯片CP2102，所以可以直接通过USB接口下载或更新固件。

MWbalanced使用STC15单片机内部时钟@33M，所以要对STC-ISP做以下设置，如图1所示。

![](/img/wiki/stc-isp-download.png)

图1

烧录成功后，STC-ISP会有操作成功提示。如图2所示。

![](/img/wiki/stc-isp-download-success.png)