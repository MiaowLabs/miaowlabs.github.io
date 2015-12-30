t---
layout: wiki
title: 新建工程
---

# {{ page.title }}

> 作者：Songyimiao

##获取IAP15头文件

这些由芯片厂商发布的文件，通过官网途径获取就最是便捷啦。

有两个简便的方法：

一个方法是，打开STC-ISP下载工具，在右边选项卡里选择“Keil仿真设置”，点击“添加型号和头文件到Keil中”，可以把STC现有大部分芯片的头文件包含进去。

![](/img/wiki/new-project-01.png)

第一种方法

另一个方法是，打开STC-ISP下载工具，在右边选项卡里选择“头文件”，在“单片机系列”中选择要用到的芯片型号，我们在这里选“STC15W4Kxx/IAP15W4K61S4/IRC15W4K63S4 Series”，就可以看到对应的头文件，再复制代码或者保存文件，放进工程。

![](/img/wiki/new-project-02.png)

第二种方法

##开始新建工程

1、第一步，点击桌面Keil C51图标，启动软件。如果是第一次使用的话会打开一个自带的工程文件，我们可以通过工具栏 Project->Close-Project选项把它关掉。
2、在工具栏 Project->New μVision Project新建我们的工程文件。
3、我们将新建的工程文件保存在一个文件夹里面。首先我们建一个名为工程模板的文件夹，再在工程模板里面建几个文件夹（如下图所示）： Appcode、BSP、Common、Driver、Listing、Output 、Startup。

![](/img/wiki/new-project-03.png)

4、直接将工程保存在上一步骤建立的工程模板文件夹，其中工程名字我在这里取为MWbalanced，大家可以根据自己的爱好取名字，不必跟我一样。

![](/img/wiki/new-project-04.png)

5、（进行这一步骤的前提是已经获取了STC15的头文件噢，还没有就参考上面的获取STC头文件的方法）接下来的窗口是让我们选择CPU数据库，选择STC MCU Database。接着，要我们选择公司跟芯片的型号，我们用的芯片是STC公司的IAP15W4K61S4，属于STC15W4K32S4系列芯片，按如下选择即可。

![](/img/wiki/new-project-05.png)


![](/img/wiki/new-project-06.png)

6、接下来的窗口问我们是否需要拷贝8051的启动代码到工程文件中，这份启动代码在8051系列中都是适用的，一般情况下我们都点击是。点击“是”后，Keil会在工程里自动添加“STARTUP.A51”启动文件。
7、此时我们的工程新建成功，如下图所示。但我们的工程中还没有任何文件，接下来我们需要在我们的工程中添加所需文件。

![](/img/wiki/new-project-07.png)

8、在工程模板文件夹下，我们在刚开始建的文件夹下添加我们所需要的文件。

![](/img/wiki/new-project-08.png)

Appcode用来存放用户写的驱动文件。其中还包含了下面这四个文件：
main.c、isr.c、carstand.c、carstand.h、includes.h。

![](/img/wiki/new-project-09.png)

BSP用来存放底层配置头文件。其中包含两个头文件：IAP15W4K61S4.h、IOConfig.h。

![](/img/wiki/new-project-10.png)

Common包含通用资源文件，其中inc文件夹是头文件，src文件夹是驱动文件（c文件）。

![](/img/wiki/new-project-11.png)

Driver里面也有inc和src这两个文件夹，这两个文件夹用来存放STC芯片的驱动。

![](/img/wiki/new-project-12.png)

Startup里面是启动文件，即包含STARTUP.A51。

![](/img/wiki/new-project-13.png)

Output用来保存软件编译后输出的文件，当我们编译出hex文件就放在这个文件夹。

![](/img/wiki/new-project-14.png)

Listing用来存放一些编译过程中产生的文件。

UpdateLog.txt文件用来记录更新等。

![](/img/wiki/new-project-15.png)

现在我们就已经基本完成了往模板里面添加库文件的工作。


