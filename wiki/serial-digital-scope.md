---
layout: wiki
title: 虚拟示波器Serial Digital Scope
---

# {{ page.title }}

> 作者：Songyimiao

我们的上位机尚在调试当中。所以，暂用一款虚拟示波器Serial Digital Scope V2作为我们的调试工具，可以用于观察波形。

下面为大家讲解如何使用虚拟示波器Serial Digital Scope V2。

##驱动安装

1. 安装串口驱动。MWbalanced板载CP2102，选择对应的驱动，傻瓜式安装，一路next到底即完成安装。
2. 准备一根micro USB 数据线，即常见的手机数据线。
3. 完成上面两个步骤后，通过数据线连接到电脑上。电脑会自动识别设备安装驱动（要先完成第一步预安装喔），在我的电脑--设备管理器--端口处找到相关串口显示。Serial Digital Scope V2原版软件需要收费，只能免费使用COM1和9600波特率。如果串口不是COM1，点击串口驱动，右键-属性-端口设置-高级-COM端口号修改为COM1。破解版可以随意调整COM口和波特率。我们使用破解版。
4. 通过上面步骤，我们的硬件通信已经OK了。接下来就是调用API，让单片机来发送数据给上位机就可以了。

##调用API
资料包里有编写好的API，你只要加入到你的软件里面，调用即可。
![](/img/wiki/serial-digital-scope-03.png)

如果是直接使用我们喵呜实验室的代码，则已经包含API，不需要重复调用。

把相应的API加入工程之后，需要修改void OutPut_Data(void)函数，只需要改动一处，改成对应的代码，认真看下面代码，在需要改动的地方，我标注了注释。

	void OutPut_Data(void)
	{
	int temp[4] = {0};

	unsigned int temp1[4] = {0};
	unsigned char databuf[10] = {0};
	unsigned char I;
	unsigned short CRC16 = 0;
	for(i=0;i<4;i++)
	{
    
	temp[i]  = (int)OutData[i];
	temp1[i] = (unsigned int)temp[i];
    
	}
   
	for(i=0;i<4;i++) 
	{
	databuf[i*2]   = (unsigned char)(temp1[i]%256);
	databuf[i*2+1] = (unsigned char)(temp1[i]/256);
	}
  
	CRC16 = CRC_CHECK(databuf,8); 
	databuf[8] = CRC16%256;
	databuf[9] = CRC16/256;
  
	for(i=0;i<10;i++)
    UART1SendByte(databuf[i]);//需要修改的地方，改成你所用单片机串口的一字节发送函数 
	}

Serial Digital Scope V2支持四个通道。需要发送的4个数据分别写入到数组OutData[]即可，你想发送什么数据就自己成对应的，接着调用`OutPut_Data()`函数完成发送。
例如：

	OutData[0] = g_fCarAngle;//发送数据融合后角度
	OutData[1] = g_fGravityAngle;//发送加速度计角度
	OutData[2] = g_fGyroAngleSpeed;//发送陀螺仪角速度
	OutData[3] = 90；
	OutPut_Data();
喵呜实验室的代码里面，在`ISR.C`里面有调用了上面代码，并使用预编译，在需要调用API发送数据时，只需要把`#if 0`改为`#if 1`就使能调用啦。

如果不清楚什么是预编译的话，那就要打你的屁屁了，这可是C语言的基础啊。

##熟悉界面

来熟悉一下Serial Digital Scope V2的界面：

![](/img/wiki/serial-digital-scope-01.png)

上面一排工具栏的功能依次为：

![](/img/wiki/serial-digital-scope-02.png)

打开文件夹，保存文件，恢复，暂停，移动，调焦，放大，缩小，X轴调节，Y轴调节，缩小到合适图像，缩放到最大等功能。

![](/img/wiki/serial-digital-scope-04.png)

一共四个通道。想使能相应的通道，让其数据表示出来，就打上勾。

![](/img/wiki/serial-digital-scope-05.png)

**在连接好硬件和调用API后，点击RUN即可显示数据。**