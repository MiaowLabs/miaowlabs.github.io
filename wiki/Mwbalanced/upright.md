---
layout: wiki
title: 平衡小车直立控制调试
---

# {{ page.title }}

> author：Songyibiao

平衡小车由角度环和速度环控制。其中，角度环为内环，速度环为外环。

角度环使用PD（比例微分）控制器，其实一般的控制系统，例如水温控制，单纯的P控制或者PI控制就够用了，但是那些对干扰要做出迅速响应的控制过程需要D（微分）控制。

下面是直立PD控制的代码：

	/***************************************************************
	** 作　  者: Songyibiao
	** 官    网：http://www.miaowlabs.com
	** 淘    宝：http://miaowlabs.taobao.com
	** 日　  期: 2015年11月29日
	** 函数名称: AngleControl
	** 功能描述: 角度环控制函数           
	** 输　  入:   
	** 输　  出:   
	** 备    注: 
	********************喵呜实验室版权所有**************************
	***************************************************************/
	void AngleControl(void)	 
	{  
		//去除零点偏移,计算得到加速度传感器的角度（弧度）
		g_fGravityAngle = (float)(g_iAccelInputVoltage_X_Axis - GRAVITY_OFFSET) / 16384.0f;
		// 57.2957795=180/3.1415926535898 弧度转换为度
		g_fGravityAngle = g_fGravityAngle * 57.2957795f ;
		//陀螺仪去零点偏移，乘比例因子
		g_fGyroAngleSpeed = (g_iGyroInputVoltage_Y_Axis - GYRO_OFFSET) / GYROSCOPE_ANGLE_RATIO *(-1.0);
		//互补滤波
		g_fCarAngle = 0.99f*(g_fCarAngle + g_fGyroAngleSpeed * 0.008f) + 0.01f * g_fGravityAngle;
		//角度环PID控制
		g_fAngleControlOut = (CAR_ANGLE_SET - g_fCarAngle)* g_tAnglePID.P+ \
		(CAR_ANGULARSPEED_SET - g_fGyroAngleSpeed )* g_tAnglePID.D;	   
	}

代码共五行，第一、二行是对加速度值的处理，第三行是对陀螺仪的处理，第四行是互补滤波，对加速度和陀螺仪数据进行数据融合，第五行是PID控制器计算。
	
其中，g_iAccelInputVoltage_X_Axis、g_iGyroInputVoltage_Y_Axis为MPU6050的加速度和陀螺仪数据，这里用了X轴加速度和Y轴陀螺仪。具体使用哪个轴，要看MPU6050的安装方位。

GRAVITY_OFFSET是小车的机械中值，所谓机械中值，把平衡小车放在地面上，绕电机轴旋转平衡小车，找到接近平衡的（能直立一两秒）角度，查看这时加速度的值，就是机械中值，这时应该为0，这时看到的不为0的任何值就是偏移值，所以要减去这个零点偏移。16384.0f是固定转换值，具体可以看MPU6050的规格书。

同样，陀螺仪也要减去零点偏移，并且乘于一个比例因子，这个GYROSCOPE_ANGLE_RATIO比例因子是不完全跟规格书里的，而是一个工程值，需要根据具体情况来选取，这个后面说明。接着，就是互补滤波，互补滤波比较简单，一条公式就可以妥妥的干活。不明白互补滤波工作原理的同学，自己到喵呜实验室官网看Mwbalanced 8051百科里面的教程。

最后是PID控制器计算角度环PWM输出值。

在调试直立环的时候，我们要屏蔽速度环和转向环。除了角度环，其他函数先屏蔽就行。

	SampleInputVoltage();		//采集数据函数
	AngleControl();				//直立控制函数			
	//GetMotorPulse();			//采集脉冲函数
	//SpeedControl();			//速度控制函数	
	MotorOutput();				//电机输出函数

