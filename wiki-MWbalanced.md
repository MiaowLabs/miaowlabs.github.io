---
layout: wiki
title: MWbalanced Wiki
---

<div class="jumbotron">
<b>
    <p class="lead">这里是喵呜实验室的维基百科。</p>
    <p class="lead">我们提供DIY一个属于你自己两轮自平衡小车的文档，也提供对MWbalanced两轮自平衡小车进行二次开发的指导。 </p>
</b>
</div>

<p>MWbalanced是喵呜实验室的两轮自平衡小车的代号。代号MWbalancedSTC15的命名遵循“MW+xxx”的方式，MW为大写，是Miaow的缩写，balanced为小写，意为“平衡的”，STC15是该版本使用的控制芯片型号。</p>

<h2>扫盲</h2>
* [两轮平衡车历史回顾](wiki/self-balanced-history.html)
* [开创历史的Segway](wiki/segway.html)

<h2>《零基础制作两轮自平衡小车-基于MWbalancedSTC15（第二版）讲解》</h2>
* [给初学者的一堂公开课](wiki/open-class.html)
* [教你怎么连接蓝牙遥控小车](wiki/bluetooth-connect.html)
* [教你通过USB烧写固件](wiki/usb-download-firmware.html)
* [教你使用懒人工具&固件烧写软件STC-ISP（及常见问题）](wiki/stc-isp-use-guide.html)
* [教你使用虚拟示波器Serial Digital Scope显示数据波形](wiki/serial-digital-scope.html)
* [两轮自平衡小车的数学建模](wiki/Mathematical-Modeling/MWbalanced-Mathematical-Modeling.html)
* [基础教程：MWbalancedSTC15(第二版)硬件原理图讲解](wiki/hardware-basic-2.html)
* [基础教程：MWbalanced软件框架讲解—裸机版本](wiki/software-main-none.html)
* [基础教程：为什么要用加速度计和陀螺仪两种传感器？](wiki/why-accel-gyro.html)
* [基础教程：两轮自平衡小车需要用到多少个维度数据？](wiki/how-many-dimensions.html)
* [基础教程：简单有效的互补滤波器](wiki/complementary-filter.html)
* [基础教程：在Windows平台下搭建开发环境](wiki/setup-environment.html)
* [基础教程：新建Keil工程模板](wiki/new-project.html)
* [基础教程：LED指示灯实验](wiki/LED.html)
* [基础教程：串口通讯实验](wiki/uart.html)
* [基础教程：（蓝牙）无线通讯实验](wiki/bluetooth.html)
* [基础教程：传感器数据采集实验](wiki/mpu-6050.html)
* [基础教程：PWM驱动电机实验(待上传)]()
* [基础教程：编码器数据采集实验(待上传)]()
* [进阶教程：多传感器数据融合(待上传)]()
* [进阶教程：使用PID算法控制电机速度(待上传)]()
* [进阶教程：角度环PD调试指南](wiki/angle-pd.html)
* [进阶教程：速度环PI调试指南(待上传)]()
* [进阶教程：方向环PD调试指南(待上传)]()
* [进阶教程：红外巡线(待上传)]()


<h2>MWbalanced选型指南（第一版）</h2>
* [MWbalanced(第一版)零部件购买指南](wiki/devices-buy.html)
* [MWbalanced元器件选型总览](wiki/devices-selection.html)
* [MWbalanced电机选型](wiki/motor-select.html)
* [MWbalanced电池选型](wiki/power-select.html)

<h2 id="rd">开发指南</h2>
* [windows下开发环境搭建—裸机版本](wiki/setup-environment-in-windows-none.html)
* [windows下开发环境搭建—Small RTOS51版本]()

<h2>MWbalanced原理讲解</h2>
* [MWbalanced硬件原理讲解](wiki//hardware-basic.html)
* [MWbalanced软件开发经验总结](wiki/)
* [MWbalanced通信协议](wiki/)

<h2 id="exp">开发经验总结</h2>
* [原地直立&原地旋转](wiki/MWbalanced-inplace-hold.html)
* [动力效率&续航时间](wiki/MWbalanced-power-endurance.html)
* [车体平衡调试](wiki/MWbalanced-debug.html)
* [超声波和避障]()
* [红外巡线]()
* [摄像头和图传]()

<h2 id="quadcopter-dev">两轮自平衡小车算法讲解</h2>
<p>姿态解算是指把陀螺仪、加速度计等数据融合在一起，得到平衡小车的姿态数据，也叫做姿态融合。姿态解算的过程，涉及到传感器数据读取与滤波，四元数与旋转，姿态解算框架，长期融合/快速融合。</p>
* [为什么要用加速度计和陀螺仪两个传感器？](wiki/why-accel-gyro.html)
* [两轮自平衡小车需要用到多少个维度数据？](wiki/how-many-dimensions.html)
* [互补滤波器](wiki/complementary-filter.html)
* [软件姿态解算]()
* [硬件姿态解算]()
* [三轴陀螺仪和三轴加速度计MPU6050]()
* [平衡车PID控制算法](wiki/algorithm-pid.html)

<h2 id="crazyflie">Small RTOS51</h2>
<p>为了满足各个层次小伙伴的需求和体现出我们的努力，后续会试着移植Small RTOS51实时操作系统内核。Small RTOS51是陈明计先生编写的一个实时操作系统，并著有《嵌入式实时操作系统Small RTOS51原理及应用》。SmallRTOS51适合在小RAM/小FLASH单片机上运行。</p>
* [Small RTOS51简介](wiki/smallrtos51-intro.html)
* [介绍几个常用的宏的作用]()
* [固件系统流程框架]()
* [通信协议]()

<h2 id="other">其他</h2>
* [MWbalanced的机械结构](wiki/MWbalanced-structure.html)
* [MPU-6050芯片解剖](wiki/mpu6050-anatomy.html)
