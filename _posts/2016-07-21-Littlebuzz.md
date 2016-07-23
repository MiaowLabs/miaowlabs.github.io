---
layout: blog-post
title: Littlebuzz微型四轴飞行器
author: songyibiao
description: 喵呜实验室Miaowlabs的开源微型四轴飞行器Littlebuzz，选取STC15@20M(1T 8051)作为主芯片。在这里，你几乎可以学习到全部的四轴飞行器知识。
---

![](/img/blog/littlebuzz-02.jpg)

喵呜实验室的开源微型四轴飞行器Littlebuzz，选取STC15@20M(1T 8051)作为主芯片，资料整理系统，并免费发布在官网，关键是中文文档，符合国人阅读习惯。代码更新托管在Github，适合单片机初学者、电子爱好者、大学生等学习、研究。在这里，你几乎可以学习到全部的四轴飞行器知识。

![](/img/blog/littlebuzz-01.jpg)

Littlebuzz的特点：

 * 小而轻。不带电池的裸机重量：约30克；带350mAh锂电池的重量：约38克，电机轴对角尺寸：约100mm；
 * 飞行时间：约4分钟（采用标准350mAh锂电池）;
 * (STC)IAP15W4K61S4(1T 8051) @ 20MHz 处理器（61Kb flash, 4kb RAM）。
 * Invensense MPU-6050 6轴陀螺仪、加速度计:；
 * nRF24L01+模块。不带PA，遥控距离约60m，带PA，遥控距离更长，具体未测试；
 * 标准micro-USB接口。用于烧录程序和对350mAh锂电池充电，充电时间40分钟。

![](/img/blog/littlebuzz-03.jpg)
 
Littlebuzz上集成了USB-Serial芯片CP2102和Micro-USB端子。实现一键下载，随走随下的功能。


