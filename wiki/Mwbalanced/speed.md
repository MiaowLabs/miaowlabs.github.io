---
layout: wiki
title: 平衡小车速度控制调试
---

# {{ page.title }}

> author：Songyibiao

## 整体思路

下面是速度PI控制的代码代详细注释：

	/***************************************************************
	** 作　  者: Songyibiao
	** 官    网：http://www.miaowlabs.com
	** 淘    宝：http://miaowlabs.taobao.com
	** 日　  期: 2015年11月29日
	** 函数名称: SpeedControl
	** 功能描述: 速度环控制函数           
	** 输　  入:   
	** 输　  出:   
	** 备    注: 
	********************喵呜实验室版权所有**************************
	***************************************************************/
	void SpeedControl(void)
	{  
		float fDelta;
		float fP, fI;
		
		g_fCarSpeed = (float)(g_iLeftMotorPulseSigma  +  g_iRightMotorPulseSigma ) * 0.5f;//M法测速，得到80ms的脉冲数
		g_iLeftMotorPulseSigma = g_iRightMotorPulseSigma = 0;	  //全局变量 注意及时清零

		/*低通滤波*/
		g_fCarSpeed = (float)(g_fCarSpeedOld * 0.2f + g_fCarSpeed * 0.8f) ;
		g_fCarSpeedOld = g_fCarSpeed;
																 
		fDelta = CAR_SPEED_SET;//设定速度值，这里不竞速所以设为0即可
		fDelta -= g_fCarSpeed;//设定速度-当前速度=速度误差
		fP = fDelta * g_tSpeedPID.P;//计算P控制=速度误差*P值
		fI = fDelta * g_tSpeedPID.I;//计算I控制第一步=速度误差*I值
		g_fCarPosition += fI;	//计算I控制第二步，得到I控制值

		/*积分上限设限*/			  
		if((int)g_fCarPosition > SPEED_CONTROL_OUT_MAX)    g_fCarPosition = SPEED_CONTROL_OUT_MAX;
		if((int)g_fCarPosition < SPEED_CONTROL_OUT_MIN)    g_fCarPosition = SPEED_CONTROL_OUT_MIN;
	
		g_fSpeedControlOut = fP + g_fCarPosition;//最终输出速度控制PWM
	}