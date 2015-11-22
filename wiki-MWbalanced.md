---
layout: wiki
title: MWbalanced Wiki
---

<div class="jumbotron">
    <p class="lead">这里是喵呜实验室的维基百科。我们提供DIY一个属于你自己两轮自平衡小车的文档，也提供对MWbalanced两轮自平衡小车进行二次开发的指导。 </p>
</div>

<p>MWbalanced是喵呜实验室的两轮自平衡小车的代号。代号MWbalanced的命名遵循“MW+xxx”的方式，MW为大写，是Miaow的缩写，balanced为小写，意为“平衡的”。</p>
* [入手试玩教程](/manual.html)
* [组装维修教程]()

<h2 id="rd">开发指南</h2>
* [windows下开发环境搭建—裸机版本](wiki/setup-environment-in-windows-none.html)
* [windows下开发环境搭建—Small RTOS51版本]()
* [STC-ISP使用及常见问题](wiki/stc-isp-use-guide.html)
* [通过USB烧写固件]()
* [MWbalanced安卓客户端]()
* [虚拟示波器的使用]()

<h2>MWbalanced原理讲解</h2>
* [MWbalanced元器件选型总览](wiki/devices-selection.html)
* [MWbalanced零部件购买指南](wiki/devices-buy.html)
* [MWbalanced硬件原理讲解](wiki//hardware-basic.html)
* [MWbalanced软件框架讲解](wiki/)
* [MWbalanced软件开发经验总结](wiki/)
* [MWbalanced通信协议](wiki/)

<h2 id="exp">开发经验总结</h2>
* [原地直立&原地旋转]()
* [动力效率&续航时间]()
* [车体平衡调试]()
* [超声波和避障]()
* [红外巡线]()
* [摄像头和图传]()

<h2 id="quadcopter-dev">两轮自平衡小车算法讲解</h2>
<p>姿态解算是指把陀螺仪、加速度计等数据融合在一起，得到平衡小车的姿态数据，也叫做姿态融合。姿态解算的过程，涉及到传感器数据读取与滤波，四元数与旋转，姿态解算框架，长期融合/快速融合。</p>
* [姿态解算简介]()
* [姿态的数学表示方法]()
* [姿态的测量]()
* [软件姿态解算]()
* [硬件姿态解算]()
* [三轴陀螺仪和三轴加速度计MPU6050]()
* [平衡车PID控制算法]()

<h2 id="crazyflie">Small RTOS51</h2>
<p>为了满足各个层次小伙伴的需求和体现出我们的努力，后续会试着移植Small RTOS51实时操作系统内核。Small RTOS51是陈明计先生编写的一个实时操作系统，并著有《嵌入式实时操作系统Small RTOS51原理及应用》。SmallRTOS51适合在小RAM/小FLASH单片机上运行。</p>
* [Small RTOS51简介](wiki/smallrtos51-intro.html)
* [介绍几个常用的宏的作用]()
* [固件系统流程框架]()
* [通信协议]()

<h2 id="other">其他</h2>
* [MWbalanced的机械结构](wiki/mwbalanced-construct.html)
