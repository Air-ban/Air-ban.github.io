# 说在前面
最近突然心血来潮，对AI感兴趣了，经过我短暂而又不仔细的了解后，我选择了pytorch框架进行学习，本文将向你讲述，如何在Windows系统中部署pytorch环境

## 准备工作
### anaconda
首先，下载anaconda，这是一个非常好用的python虚拟环境管理工具，操作简单，建议使用，[这是下载地址](https://www.anaconda.com/download/success)

下载完后，安装，安装好后，在终端中使用``conda``指令来检查是否成功安装
![](https://images-ave.oss-rg-china-mainland.aliyuncs.com/20241013152414.png)
如图所示，在输入后返回了各种帮助操作指令，就算安装好了
### anaconda的环境配置
首先，使用这个指令创建一个虚拟环境

```nonda create -n 环境名字 python=你需要的python版本，例如3.8```

此处给出一个通用范例

```conda create -n th python=3.8```

这段指令创建了一个名为th的python3.8的虚拟环境

输入指令后，系统会自动下载并部署python环境
![](https://images-ave.oss-rg-china-mainland.aliyuncs.com/20241013152816.png)
此处输入Y

随后我们可以看到已经部署好了
![](https://images-ave.oss-rg-china-mainland.aliyuncs.com/20241013152854.png)
这里给出了使用的指令，即为```conda activate th```，使用这段指令激活环境
![](https://images-ave.oss-rg-china-mainland.aliyuncs.com/20241013153001.png)
在已激活环境的终端里面，前面会显示当前激活的环境名称

### pytorch的安装
我们首先进入[pytorch官网](https://pytorch.org/)，进去后，点击get start，在此处先择你需要的环境

![](https://images-ave.oss-rg-china-mainland.aliyuncs.com/20241013153145.png)

建议：选择stable版本，OS根据自己的电脑系统来选择，语言选择python，如果你有N卡，且型号≥GTX750ti，你可以根据自己电脑的cuda版本选择带有cuda的版本，否则，就选择CPU

选择好后直接复制下面的指令安装就好
```

pip3 install torch torchvision torchaudio

```
此处是CPU版本的安装指令，直接安装就好

随后进入python，查看pytorch是否安装完毕，直接导入torch库查看是否报错即可
![](https://images-ave.oss-rg-china-mainland.aliyuncs.com/20241013153549.png)
至此，pytorch就算是成功的被安装进电脑了

## 关于VSCODE
![](https://images-ave.oss-rg-china-mainland.aliyuncs.com/20241013153729.png)
如图所示，你可以在VScode中方便的切换各个python环境，而不需要输入指令，仅此而已