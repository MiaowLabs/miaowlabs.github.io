---
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

9、回到我们刚刚新建的工程界面，把刚刚那些文件夹里面的内容添加进
工程，这样我们在 Keil 界面里面就可以管理那些文件了。

9.1、把Target的名称改为MWbalanced， 如果我们建的工程是LED的就改为
LED，其实不改也可以，改了只是为了见名知义。

![](/img/wiki/new-project-16.png)

9.2、往工程里面添加5个组文件夹，并命名为 Appcode、Driver 、Common 、
BSP 、Startup。

![](/img/wiki/new-project-17.png)

**我们的命名方式都是尽量能顾名思义，Appcode用来存放用户自定义的应用程序,Startup从名字就可以看得出我们是用它来放我们的启动代码的，，Driver用来存放STC驱动文件， Common 用来存放通用资源文件。**

9.3、接下来我们往这些新建的组中添加文件，双击哪个组就可以往哪个组里面
添加文件，如果该组里面已经有文件的话，双击则把组里面的文件都显示
出来，然后再双击该组的话，则可以继续添加文件。

![](/img/wiki/new-project-18.png)

在对话框里面的文件类型里面我们选择 ALL files（*.*），不然有些文件会显示
不出来。

10.1、至此，我们的工程基本建好了啦。但是还有一些工作需要完成。下面来配
置一下Keil的配置选项，点击工具栏中的魔术棒按钮。

Target选项卡，Memory Model用鼠标点击Memory Model的下拉箭头，会有3个选项：

　　Small：变量存储在内部ram里；
 
    small模式下，再入函数的堆栈是设在idata中的
 
　　Compact：变量存储在外部ram里,使用页8位间接寻址；

	compact模式下，再入函数堆栈是设在pdata中的
 
　　Large：变量存储在外部Ram里,使用16位间接寻址；

**我们这里选择Memory Model选择large模式。**


	Code Rom Size：
	SMALL模式：只用低于2K的程序空间
	COMPACT模式：单个函数的代码量不能超过2K，整个程序可以使用64K的程序空间
	LARGE模式：可用全部64K空间

**Code Rom Size（设置ROM空间的使用），我们也选择large模式。**

操作系统选择none，表示不用Keil自带的操作系统。

![](/img/wiki/new-project-24.png)

10.2、Output 选项卡如下设置，点击 Select Folder for Objects... 设
置编译后输出文件保存的位置。同时把 Debug Information 、 Create HEX File
和 Browse information 这三个选项框也选上。

![](/img/wiki/new-project-19.png)

10.3、在 Listing 这个选项卡中，点击 Select Folder listings…定位到工程中的
Listing 文件夹。

![](/img/wiki/new-project-20.png)

10.4、在 Include Paths 栏里添加库文件的搜索路径，这样就可以屏蔽掉默认的搜索路
径。

![](/img/wiki/new-project-21.png)

但当编译器在我们指定的路径下 搜索不到的话还是会回到标准目录去搜索，就
像有些 ANSIC C 的库文件，如 stdin.h 、 stdio.h。

库文件路径修改成功之后如下所示：

![](/img/wiki/new-project-22.png)

到了这里就算是大功告成了。

如果在新建工程中遇到什么问题，先不要急，可先参考喵呜提供的已经源代码的工程噢。