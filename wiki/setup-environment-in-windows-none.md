---
layout: wiki
title: Windows下开发环境搭建-裸机版本
---

# {{ page.title }}

> 作者：nieyong

IDE开发工具Keil C51 V9.00下载地址：喵呜实验室百度云网盘[Keil-C51-Version-9.00.zip](http://pan.baidu.com/s/1kTKN5AZ)（5.2及以后版本）。

IDE开发工具Keil C51最新版本（C51-Version-9.54a）官方下载地址：[Keil官网下载页面](https://www.keil.com/demo/eval/c51.htm)。

平衡小车控制源代码下载地址：Github项目[MWbalanced-firmware-none](https://github.com/MiaowLabs/MWbalanced-firmware-none)。

CP2102驱动下载地址：喵呜实验室网盘[CP2102驱动](http://pan.baidu.com/s/1c08Q5AK)

STC-ISP固件烧录工具：喵呜实验室网盘[stc-isp-15xx-v6.82H](http://pan.baidu.com/s/1gd4S7M7)

## 环境配置说明
裸机版本是指没有使用RTOS的主控固件版本，由于没有使用RTOS，程序代码显得更加简单明了，开发环境配置简单，非常适合初学者使用。

裸机版本的代码使用Keil进行开发编译，下面介绍编译环境的搭建和编译过程。

## Keil C51的安装和破解
由于主控使用的是8051内核的STC15，所以必须使用带有8051编译工具链的Keil C51。喵呜实验室使用的Keil版本是Keil C51 V9.00。喵呜实验室百度云网盘提供带有8051编译工具链的Keil C51 V9.00安装文件下载，带有破解注册机和破解说明文档。大家自行下载安装。我们的电脑上是装了Keil C51，然后又安装了MDK-ARM覆盖的，不过依然可以看得到版本为9.00。

![](/img/wiki/keil-version.png)

该安装文件在Windows XP 32位系统、Windows 7 32和64位系统上测试通过。

## 源代码下载
主控固件裸机版本，裸机指没有使用实时操作系统RTOS。由于没有使用RTOS，所以代码更加简单明了，适合初学者使用。

喵呜实验室的MWbalanced项目是开源的，所有代码都托管在Github的[MWbalanced项目](https://github.com/miaowlabs)下。裸机源代码放置在[MWbalanced-firmware-none](https://github.com/MiaowLabs/MWbalanced-firmware-none)下，命名中的none表示不使用RTOS。

进入Github页面后，在右侧点击“Download ZIP”，即可下载源代码。

![](/img/wiki/download-zip.png)

## 源代码导入和编译
在源代码中，有4个文件为Keil工程文件。

~~~
MWbalanced-firmware-none.plg
MWbalanced-firmware-none.uvopt
MWbalanced-firmware-none.uvproj
MWbalanced-firmware-none_uvproj.bak
~~~

以Keil C51 9.00为例，点击Project栏目下Open project，打开代码解压所在文件夹选中MWbalanced-firmware-none.uvproj，此时已将代码项目工程所有文件导入Keil C51，如图所示：

![](img/wiki/keil-build.png)

点击左上角的编译按钮，编译整个项目，在工程下生成Output目录，目录中MWbalanced-firmware-none.hex就是可以烧写到STC51的固件。

STC15固件的调试和烧入可以使用STC-ISP调试器进行开发，详见[STC-ISP的使用及常见问题]()。MWbalanced板载USB-TTL芯片，支持USB口烧入，即采用ISP下载，操作简单。只需要安装cp2102驱动程序，使用一根Mini USB数据线连接电脑。详见[固件烧写]()，烧录界面如图所示:

![](img/wiki/stc-isp-download.png)

