---
layout: wiki
title: 蓝牙连接指南
---

# {{ page.title }}

> 作者：Songyimiao

MWbalanced选用了HM-13蓝牙模块，兼容SPP（蓝牙2.1）和BLE（蓝牙4.0）。

![](/img/wiki/bluetooth-connect-01.png)

图1

使用该模块要注意以下两点：

* 默认出厂波特率115200, N, 8, 1。

* 双模包含两个蓝牙地址，有些手机会搜到两个地址，00:0E:0B开头的是BLE模式的地址，00:0E:0E开头的是EDR地址。

##MWbalanced连接手机蓝牙

以下演示使用的安卓手机是小米4，使用MWbalanced官方APP。Android版APP：[下载地址](http://pan.baidu.com/s/1eRxOPsI)；iOS版APP暂未推出。



第一步，先开启手机蓝牙，搜索蓝牙设备。双模包含两个蓝牙地址，有些手机会搜到两个地址， 00:0E:0B开头的是BLE模式的地址，00:0E:0E开头的是EDR地址。如图2-1、2-2。

![](/img/wiki/bluetooth-connect-02-01.png)

图2-1

![](/img/wiki/bluetooth-connect-02-02.png)

第二步，点击要连接的蓝牙设备，输入密码（默认1234），将手机和蓝牙设备配对好。如果是出现两个地址，如果您不确定哪一个，两个地址都分别输入密码试一遍。如图3。

![](/img/wiki/bluetooth-connect-03.png)

图3

第三步，打开MWbalanced APP。如图4。

![](/img/wiki/bluetooth-connect-04.png)

图4

第四步，先点击“更新蓝牙”，然后在下方选择配对好的蓝牙设备。如图5、6。

![](/img/wiki/bluetooth-connect-05.png)

图5

![](/img/wiki/bluetooth-connect-06.png)

图6

第五步，点击“连接蓝牙”，连接成功后，蓝牙状态为“true”。如图7。

![](/img/wiki/bluetooth-connect-07.png)

图7

至此，已经成功将手机与MWbalanced的蓝牙连接好啦。尽情遥控吧，奔跑吧，直立小车！