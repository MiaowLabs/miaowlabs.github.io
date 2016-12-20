---
layout: wiki
title: 开发环境搭建-裸机版本
---

# {{ page.title }}

> 作者：Songyimiao

IDE开发工具Keil C51 V9.00下载地址：喵呜实验室百度云网盘[Keil-C51-Version-9.00.zip](http://pan.baidu.com/s/1kTKN5AZ)

IDE开发工具Keil C51最新版本（C51-Version-9.54a）官方下载地址：[Keil官网下载页面](https://www.keil.com/demo/eval/c51.htm)。

MWbalanced控制源代码下载地址：Github项目[MWbalanced-firmware-none](https://github.com/MiaowLabs/MWbalanced-firmware-none)。

CP2102驱动下载地址：喵呜实验室百度云网盘[CP2102驱动](http://pan.baidu.com/s/1c08Q5AK)

STC-ISP固件烧录工具：喵呜实验室百度云网盘[stc-isp-15xx-v6.82H](http://pan.baidu.com/s/1bnBg2qN)

## 环境配置说明

在拿到MWbalanced之后，很多朋友都跃跃欲试，想自己烧写个程序到小车控制板上，看看效果。

下面我们将演示如何将程序烧写到MWbalanced上。前提是，我们的电脑上已经安装CP2102驱动和Keil C51，没有安装的朋友请参考我们的教程。我们提供的代码都是已经编译好的，直接下载即可，如果不行，请重新编译一次。

裸机版本是指没有使用RTOS的主控固件版本，由于没有使用RTOS，程序代码显得更加简单明了，开发环境配置简单，非常适合初学者使用。

裸机版本的代码使用Keil C51进行开发编译，下面介绍编译环境的搭建和编译过程。

## Keil C51的安装和破解

由于主控使用的是8051内核的STC15，所以必须使用带有8051编译工具链的Keil C51。喵呜实验室使用的Keil版本是Keil C51 V9.00。喵呜实验室百度云网盘提供带有8051编译工具链的Keil C51 V9.00安装文件下载，带有破解注册机和破解说明文档。大家自行下载安装。我们的电脑上是装了Keil C51，然后又安装了MDK-ARM加以覆盖的，不过依然可以看得到版本为9.00。

![](/img/wiki/keil-version.png)

该安装文件在Windows XP 32位系统、Windows 7 32和64位系统上测试通过。



