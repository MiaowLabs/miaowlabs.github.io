---
layout: wiki
title: 如何编译代码
---

# {{ page.title }}

> 作者：Songyimiao

## 导入源代码

在源代码中，有4个文件为Keil工程文件。

~~~
MWbalanced-firmware-none.plg
MWbalanced-firmware-none.uvopt
MWbalanced-firmware-none.uvproj
MWbalanced-firmware-none_uvproj.bak
~~~

以Keil C51 9.00为例，点击Project栏目下Open project，打开代码解压所在文件夹选中MWbalanced-firmware-none.uvproj，此时已将代码项目工程所有文件导入Keil C51，如图所示：

![](/img/wiki/keil-build.png)

点击左上角的编译按钮，编译整个项目，在工程下生成Output目录，目录中MWbalanced-firmware-none.hex就是可以烧写到STC15的固件。

STC15固件烧入可以使用STC-ISP。，详见[STC-ISP的使用及常见问题]()。MWbalanced板载USB-TTL芯片，支持USB口烧入，即采用ISP下载，操作简单。只需要安装CP2102驱动程序，使用一根Mini USB数据线连接电脑。详见[固件烧写]()，烧录界面如图所示:

![](/img/wiki/stc-isp-download.png)









