# 说在前面
>没电脑的，请直接退出此教程，谢谢！在ROOT的操作过程中，85%的步骤都依靠电脑，没电脑是不行的，所以不要浪费自己的时间，谢谢！
## 什么是root
此处引用百科
>手机ROOT通常是指针对Android系统的手机而言，它使得用户可以获取Android操作系统的超级用户权限。root通常用于帮助用户越过手机制造商的限制，使得用户可以卸载手机制造商、运营商、第三方渠道商预装在手机中某些应用，以及运行一些需要超级用户权限的应用程序。Android系统的root与Apple iOS系统的越狱相似。

说白了就是获得最高权限，和Linux系统中的root用户类似
## 为什么要root？
其实我并不想和你大费周章，为什么root，这个理由多了去了，开挂，优化系统，抑或是一些特殊职业的特殊需求，都可能需要root来达成
>虽然理由千奇百怪，但最好不建议用作非法用途
## root常用工具
现在通常使用magisk进行root以及root后的权限管理，这里就拿magisk作为例子

magisk是一个开源项目，你可以在GitHub中找到开放源代码仓库：[magisk](https://github.com/topjohnwu/Magisk)
目前的最新版本是v27.0（截至2024/6/25）
### root具体步骤
***首先请确保你的手机已经解锁boot loader***，这一步至关重要，如何知道自己的手机是否解锁？请自行通过后续步骤进行测试

现在，就假设你什么都不懂，请根据我的后续步骤一步一步操作，不要认为自己假聪明。不要超前或滞后操作

#### 第一步：
在手机中下载并安装magisk，此处为[下载链接](https://mrzzoxo.lanzoue.com/iEiWb1s6quif)，此处为蓝奏云网盘，不挂GitHub原始链接是怕某些用户无法正常访问GitHub，此处为[GitHub原始下载链接](https://github.com/topjohnwu/Magisk/releases)如果担心软件被篡改或植入木马，请通过此链接进行下载，下载好后直接安装即可

#### 第二步：
现在打开你手机上的的magisk软件，应当是和截图中一样，版本号可以不同，但请确保其他部分相同![Screenshot_20240625-181833_Magisk.png](https://img.picui.cn/free/2024/06/25/667a997262d4d.png)
然后我们此时查看一下自己的手机是**什么系统以及什么版本**，此处是在刷写前最为重要的步骤，请一定确保版本正确无误，此处以最新的[hyperOS](https://hyperos.mi.com/ "这狗屎玩意还真有人用")举例，首先查看自己的手机型号，再查看系统版本号，此处如图所示![aa08b9dbc90032dac2fa907eb72d7826.jpeg](https://img.picui.cn/free/2024/06/25/667a9b9fa17c0.jpeg)
我们在这张图中需要获得两个信息
1. 手机型号，此处为Redmi K70
2. 手机所搭载系统版本，此处为hyperOS1.0.4.0.UNKCNXM

在获得上述信息后，将手机放到一边，进行下一步

### 第三步：
打开手机对应的系统下载网站，进行对应版本的系统下载，此处推荐下载卡刷包，当然，卡刷包或者线刷包都是没问题的，此处小米系手机对应[XIAOMIROM](https://xiaomirom.com/)，当然肯定还有一加用户，一加用户对应这位大叔的[网盘](https://yun.daxiaamu.com/OnePlus_Roms/)

首先，点击上面的链接进入xiaomirom,点击中间的搜索框，搜索对应机型，例如此处为K70则直接搜素K70即可![1719312154176.png](https://img.picui.cn/free/2024/06/25/667a9ecf48b6f.png)
![1719312227006.png](https://img.picui.cn/free/2024/06/25/667a9f08bfabc.png)
直接点击***国行版***进入即可，在下一个页面中翻找**对应**的系统版本，找到后点击下载
![1719312295553.png](https://img.picui.cn/free/2024/06/25/667a9f59ae718.png)
此处通常下载recovery卡刷包，点击小米官方即可开始下载
![1719312351334.png](https://img.picui.cn/free/2024/06/25/667a9f91b3fb2.png)
当然，你们可能会遇到下载速度过于感人，此处可以参考此[教程](https://magiskcn.com/mi-hosts)以解决问题

然后就是漫长的下载，下载完成后，是一个压缩包，我们需要把他解压出来，使用正常的解压缩软件解压即可，如图所示![1719313282484.png](https://img.picui.cn/free/2024/06/25/667aa334b4b0b.png)
![1719313387553.png](https://img.picui.cn/free/2024/06/25/667aa37bede85.png)
里面这几个文件，你都不需要在乎，你需要ROOT，那么你只需要在乎`payload.bin`这个文件，此处我们需要下载payload-dumper这个软件，此处是[下载链接](https://mrzzoxo.lanzoue.com/b02plgdpi)，根据个人系统版本，按需下载，下载完后解压出来，内容如图所示![1719313647509.png](https://img.picui.cn/free/2024/06/25/667aa4a2cc7a7.png)
接下来，将你刚刚解压出来的`payload.bin`放到这个文件夹中，如图所示![1719313745754.png](https://img.picui.cn/free/2024/06/25/667aa503c0988.png)
点击`打开CMD命令行.bat`后，如图所示![1719313828406.png](https://img.picui.cn/free/2024/06/25/667aa55680588.png)
里面给了三个选项，选哪个呢？此处具体查看你的手机处理器，如下表所示
| 处理器 | 对应提取文件 | 对应输入字母 |
| :----: | :----: | :---: |
| 骁龙8gen1 | boot.img | b |
| 骁龙8gen1+ | boot.img | b |
| 骁龙8gen2 | init_boot.img | i |
| 骁龙8gen3 | init_boot.img | i |
| 天玑9200+ | init_boot.img | i |

此处根据出场搭载系统内核版本确定，此处使用处理器确定，只是为了方便小白用户查阅并使用，原因是
> 对于发布时搭载 Android 13 的设备，通用 ramdisk 将从 boot 映像中移除，并放置在单独的 init_boot 映像中

此处是[安卓官方文档](https://source.android.google.cn/docs/core/bootloader/partitions/generic-boot?hl=zh-cn)，所以，只要你的手机处理器发布年份小于骁龙8gen1+的发布年份，就请无脑提取`boot.img`

好的，此处我们为K70，处理器为**骁龙8gen2**我们应当提取`init_boot.img`直接输入字母`I`后按下回车即可，随后会自动打开提取好后的文件夹，里面有我们心心念念的`init_boot.img`，如图所示![1719314727806.png](https://img.picui.cn/free/2024/06/25/667aa8d97f8ab.png)
接下来，我们将手机与电脑通过数据线连接，并且在手机上选择文件传输模式，将刚刚提取出来的`init_boot.img`放到手机的download文件夹中，如图所示
![1719315128837.png](https://img.picui.cn/free/2024/06/25/667aaa6aca255.png)
然后我们将镜像文件复制到Download文件夹中
![1719315041772.png](https://img.picui.cn/free/2024/06/25/667aaa13d8d37.png)
OK，现在你的手机上已经有了原始的`init_boot.img`文件，现在只需要通过使用magisk修补即可
### 第四步：
接下来，打开你手机中的magisk软件，点击第一个方框中的安装，如图所示![1719315412033.png](https://img.picui.cn/free/2024/06/25/667aab8645d58.png)然后选择`选择并修补一个文件`如图所示![1719315492281.png](https://img.picui.cn/free/2024/06/25/667aabd66037e.png)接下来，你会进入系统文件夹，别慌了神，记得上文中我们把`init_boot.img`放哪了吗？对，就是Download文件夹，进去，选择刚刚放进来的`init_boot.img`文件，如图所示![1719315648082.png](https://img.picui.cn/free/2024/06/25/667aac734184a.png)
然后我们选择`init_boot.img`如图所示![1719315718132.png](https://img.picui.cn/free/2024/06/25/667aacb8338fc.png)
然后点击`开始`，如图所示![1719315776525.png](https://img.picui.cn/free/2024/06/25/667aacf2614d7.png)
然后等待，当看到如下输出的时候，即可关闭magisk软件
>-All done!

如图所示![1719315918833.png](https://img.picui.cn/free/2024/06/25/667aad80c4b87.png)
好的，现在使用数据线连接手机和电脑，并且在手机中选择文件传输，如上文所述，然后我们和上文一样，打开手机的Download文件夹，你就会看到一个`magisk_patched-27000_XXXXX.img`的文件，将文件复制到电脑任意位置，此处建议直接复制到桌面，方便后续操作，如图所示![1719316146038.png](https://img.picui.cn/free/2024/06/25/667aae644afbc.png)
现在复制到桌面，如图所示![1719316211208.png](https://img.picui.cn/free/2024/06/25/667aaea5630de.png)
### 第五步：
**这是最重要的一步，所以请一定按照指示进行操作**

首先下载adb工具集，此处是[Google官方下载链接](https://googledownloads.cn/android/repository/platform-tools-latest-windows.zip)，下载好后，将里面所有的内容解压到一个文件夹中，如图所示![1719316472372.png](https://img.picui.cn/free/2024/06/25/667aafac39e3d.png)
接下来，安装所需驱动，此处是一键安装程序的[下载链接](https://www.lanzouw.com/i7hucfg)，下载后解压打开，直接点击安装即可，如图所示 

![1](https://img.ddooo.com/uppic/20231216/f515f9b06010c387600d392a2c6f3d13.png)

然后此时，我们回到刚刚的adb文件夹中，我们直接点击文件夹上面的地址栏，在中输入`cmd`后点击回车，如图所示![image.png](https://s2.loli.net/2024/06/25/dQhbtvU84LKPkxy.png)![image.png](https://s2.loli.net/2024/06/25/YlPWSjXtRTkAiEy.png)

在cmd命令行中输入
>adb

查看输出，如果**没有**输出
>'adb' 不是内部或外部命令，也不是可运行的程序
或批处理文件。

则代表成功进入adb命令行，现在我们使用数据线连接手机与电脑，在手机上打开USB调试，如何打开USB调试建议百度，本文不过多赘述

在命令行中输入
>adb devices

会看到如下输出


![image.png](https://s2.loli.net/2024/06/25/zhimtnjf4pw8qEv.png)

如果没有看到如下输出，请检查手机是否弹出授权提示，如图所示![Screenshot_20240625-200638_.png](https://s2.loli.net/2024/06/25/NGMxVAdEPFgajWv.png)
点击允许即可

接下来，我们在刚刚的命令行中输入
>adb reboot bootloader

手机会自动重启到fastboot，接下来我们刷入刚刚修补的`init_boot.img`
>fastboot flash init_boot magisk_patched-27000_xxxx.img

注意，如果magisk修补镜像不在当前文件夹，可以直接将桌面上的magisk_patched-27000_xxxx.img拖进命令行
>fastboot flash init_boot <此处拖入修补后的文件>

随后即可完成修补镜像的刷入，随后输入
>fastboot reboot

即可重启回到系统中啦
## 注意
如果你是boot镜像，则将上述所有init_boot处换成boot，部分机型还需要换成boot_ab

boot分区
>fastboot flash boot <拖入boot镜像>

vab的boot分区
>fastboot flash boot_ab <拖入boot镜像>

如果你的手机在输入flash指令后出现了如下报错
>error: FAILED (remote: flash is not allowed in Lock State)

关键词，只要出现了notallowed in lock，十有八九就是没解锁，至于如何解锁，等我下一篇文章

# 至此END
