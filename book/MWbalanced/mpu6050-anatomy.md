---
layout: wiki
title: Invensense MPU-6050 芯片解剖
---

# {{ page.title }}

> 参考：http://zeptobars.ru/en/read/Invensense-MPU6050-6d-MEMS-IMU-gyroscope-accelerometer

InvenSense的MPU-6050集成了具有16位分辨率的陀螺仪和加速度计。它包含两个晶片，面对面地在很多地方用焊点连接（这就给我们的芯片解剖造成了麻烦，最后一次分离所需的温度超过600℃）。 如图1。

![](/img/wiki/mpu6050-anatomy-01.jpg)

图1

在全局照片上你可以看到他们是如何的不平坦。 大一点的晶片突出表面的高度有28μm，小一点的晶片超过100μm。如图2。此外，那颗大一点的MEMS晶片下方还有逻辑电路。

![](/img/wiki/mpu6050-anatomy-02.jpg)

图2 大的晶片尺寸为2782x2718μm，小的晶片尺寸为2778x2195μm。 

小晶片，对焦在顶层。宽度最小的齿列的为1μm。 

这些齿列让我们可以通过电极之间的电容变化来感知它们的运动。 如图3。

![](/img/wiki/mpu6050-anatomy-03.jpg)

图3

小晶片，对焦于底层，如图4：

![](/img/wiki/mpu6050-anatomy-04.jpg)

图4

大晶片，如图5：

![](/img/wiki/mpu6050-anatomy-05.jpg)

图5

在MEMS的下方可以很容易地找到传统的数字逻辑电路，～250nm的半间距 

SRAM，单元面积为10.13µm<sup>2</sup>，如图6：

![](/img/wiki/mpu6050-anatomy-06.jpg)

图6

基础标准单元逻辑电路，如图7：

![](/img/wiki/mpu6050-anatomy-07.jpg)

图7

