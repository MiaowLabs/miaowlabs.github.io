---
layout: wiki
title: Littlebuzz硬件原理讲解
---

# {{ page.title }}

> 作者：喵大

## Littlebuzz飞行器平台

Littlebuzz的特点：

* 小而轻。重量：克；电机轴对角尺寸：100mm；
* 飞行时间：4分钟，采用标准350mAh 20c锂电池；
* IAP15W4K61S4(1T 8051) @ 20MHz 处理器（61Kb flash, 4kb RAM）
* 6轴陀螺仪、加速度计:Invensense MPU-6050；
* nRF24L01+模块。不带PA，遥控距离70m，带PA，遥控距离更远，具体未测试；
* 标准micro-USB接口。用于烧录程序和对350mAh锂电池充电，充电时间40分钟；

# Littlebuzz原理图设计

### 单片机最小系统

单片机选择宏晶公司IAP15W4K61S4，它体积小（LQFP48），工作电压宽（2.5V-5.5V
），具有丰富的外设模块，能满足制作微型四轴飞行器的要求。

它的外设包括：

1. PWM ：6路15位硬件PWM+2路CCP的16位；
2. UART：4组；
3. ADC：8路10位高速ADC；
3. 定时器：共7个定时器，5个16位可重装载定时器/计数器,2路CCP还可再实现2个定时器；
5. IO口：最多提供62个GPIO；
6. 内部存储器资源包括： 61kb Flash，4kb SRAM。

此外，IAP15W4K61S4内部还集成了时钟电路、内部高可靠复位电路以及看门狗电路等。下图显示该单片机的内部资源情况。

![](http://miaowlabs.com/img/wiki/hardware-basic-01.png)

IAP15W4K61S4单片机内置时钟和复位电路，单片机的最小系统电路非常简洁。

![](http://miaowlabs.com/img/wiki/Littlebuzz/hardware/01.png)


## 动力电源

电池使用的是锂电池（锂离子聚合物电池），是目前流行的航模动力电池。但锂电池必须按照规定使用，过冲、过放都会产生安全隐患。航模动力电池具有最高的电能/质量比和最大的放电电流，是比较合适的选择。

航模动力电池，常见有1s 3.7v、2s 7.4v、3s 11.1v锂电池。“s”代表串联，“2s”即为两块3.7v锂电池串联，得到7.4v。

![](http://miaowlabs.com/img/wiki/Littlebuzz/hardware/10.jpg)

## 系统电源


Littlebuzz采用3.7v 350mAh锂电池。电池电压为3.7V，但系统选用芯片要求是3.3v和5v供电。3.7v无法满足所有电压需求。所以，Littlebuzz采取先用DCDC将3.7V升至5V，再用LDO降至3.3V，以满足系统电压使用要求。

![power](http://miaowlabs.com/img/wiki/Littlebuzz/hardware/02.png) 

![power](http://miaowlabs.com/img/wiki/Littlebuzz/hardware/03.png)


## 姿态传感器

Littlebuzz的姿态传感器使用的Invensens公司的MPU-6050单芯片六轴传感器，它包含了一个三轴陀螺仪和一个三轴加速度计。MPU-6050使用IIC通信，可以外挂磁力计HMC5883L，但微型四轴飞行器体积过小，电机运转起来对磁力计影响较大，使磁力计形同虚设，所以Littlebuzz没有加入磁力计。


![](http://miaowlabs.com/img/wiki/Littlebuzz/hardware/04.png)

## 驱动电路

Littlebuzz选用MOS管来驱动电机，通过PWM控制电机转速。该MOS管的驱动电路可达3A，完全满足微型四轴飞行器的设计需求。值得注意的是，MOS管要接电阻下拉，防止电机在上电时误转。


![](http://miaowlabs.com/img/wiki/Littlebuzz/hardware/05.png)


## USB-Serial协议转换

几乎每个人都有手机数据线，所以，出于节省环保和方便使用的目的，Littlebuzz上集成了USB-Serial芯片CP2102和Micro-USB端子。实现一键下载，随走随下的功能。

![](http://miaowlabs.com/img/wiki/Littlebuzz/hardware/06.png)

![](http://miaowlabs.com/img/wiki/Littlebuzz/hardware/09.jpg)

## 充电管理

难道玩一下四轴还要去额外买充电器？大麻烦了。于是，Littlebuzz集成了LTC4054单锂电池充电芯片。需要充电时，把电源开关拨至OFF/CHA端，然后把手机充电线线插入Micro-USB即可进行充电。

LTC4054外围电路简单，一个电阻R4作为充电限流电阻，充电电流最大可达600mA，充电电流计算公式：IBAT =(VPROG /RPROG)*1000。R1作为充电指示灯的限流电阻，选择几百欧姆就行了。当充电进行中，引脚CHRG常低，充电结束时，CHRG拉高。对应的状态就是：充电时，LED灯常亮，充电完成，LED 灯灭。

![](http://miaowlabs.com/img/wiki/Littlebuzz/hardware/07.png)

## 2.4G 通信

2.4G通信芯片选择大家熟悉的芯片-nRF24L01。

Littlebuzz体积紧凑，nRF24L01芯片不集成到PCB上，而是选用现成的无线模块，其接口电路和无线模块实物分别如图所示。

![](http://miaowlabs.com/img/wiki/Littlebuzz/hardware/08.png)

![](http://miaowlabs.com/img/wiki/Littlebuzz/hardware/11.jpg)