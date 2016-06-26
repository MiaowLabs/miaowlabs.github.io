---
layout: wiki
title: MWbalanced零部件购买指南
---

# {{ page.title }}

> 作者：Songyimiao

我们暂不提供零部件的购买，为了方便大家DIY自己的MWbalanced，便整理了重要的零部件&元器件的淘宝购买地址，大家可自行购买。

## 电机

GB37电机（带16CPR霍尔效应编码器）   

* 额定电压：12V
* 转速：366RPM
* 空载力矩：（待测试）
* 堵转力矩：13kg.cm
* 空载电流：250mA
* 堵转电流：6.5A
* 编码器：16CPR霍尔效应编码器(AB相正交输出)

购买地址：[淘宝链接](https://item.taobao.com/item.htm?spm=a1z09.2.0.0.Q3DKNu&id=6213751132&_u=mqnqfnb419f)

## 轮子

1:10模型比例65mm轮胎  

购买地址：[淘宝链接](https://item.taobao.com/item.htm?spm=a230r.1.14.47.d2ooXZ&id=18755461026&ns=1&abbucket=15#detail)


## 电池

MWbalanced所配锂电池容量1300mAh，电压11.1V，放电倍率25C。大家也可以选择更大容量电池，从而获得更长续航时间。

购买地址：[淘宝链接](https://item.taobao.com/item.htm?spm=a1z09.2.0.0.EBWjeX&id=17076820898&_u=mqnqfnb7166)

购买时需要注意电池接口。

## 蓝牙透传模块

双模蓝牙模块HM-13，兼容蓝牙2.1和蓝牙4.0。

[淘宝链接](https://item.taobao.com/item.htm?spm=a1z09.2.0.0.EBWjeX&id=40978109020&_u=mqnqfnb5ba7)，仅此一家。

## MCU

控制芯片为STC15系列1T 8051单片机。IAP15W4K61S4，4K SRAM，8051内核，33MHz主频，61K Flash，LQFP48封装。

>STC的IAP系列单片机，和STC系列单片机的不同之处在于，整颗MCU的Flash空间，用户可在自己的程序中进行改写，开发用户自己的ISP程序。例如改写用户bootloader，实现无线升级固件等功能。

## 传感器

MPU6050，三轴陀螺仪+三轴加速度传感器，自带DMP四元数输出，内部温度补偿。

## 电机驱动

MC33186，Freescale生产，单H桥芯片，工作电压5V-28V，兼容TTL/CMOS输入，PWM频率可达20kHz，输出电流限制在6.5A±20%，输出电流超过8A时启动输出短路保护。

## USB-UART桥接器

CP2102，是一款高度集成的USB-UART桥接器，用于固件下载，参数调试。

## 拨动开关

MTS102，6A/125V，大电流开关。

![](/img/wiki/devices-buy-01.png)






