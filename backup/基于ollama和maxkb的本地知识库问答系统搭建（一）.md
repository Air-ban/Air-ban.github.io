# 说在前面
本项目当然可以使用本地电脑，甚至可以较为落后的CPU，不过响应速度很感人，如果可以，建议使用API或者云服务器，如果一定需要确保信息的私密性，请确保本地硬件性能以确保体验
## 一，软件准备
此处为ollama官网：https://ollama.com/
此处为maxkb的GitHub项目页：https://github.com/1panel-dev/MaxKB
此处为docker官网：https://www.docker.com/
## 二，准备工作
### 1.安装docker环境 
首先，需要安装docker服务，但是在此之前，你需要启动WSL服务，如果你是Linux，请直接安装docker，Windows系统请按图示启动WSL服务
![step1](https://images-ave.oss-rg-china-mainland.aliyuncs.com/QQ_1720675373852.png)
![step2](https://images-ave.oss-rg-china-mainland.aliyuncs.com/QQ_1720675407157.png)
打勾后点击确定，重启电脑即可

然后我们在WSL中安装系统，直接使用WSL install命令即可，如图所示
![step3](https://images-ave.oss-rg-china-mainland.aliyuncs.com/step3.png)

如果懒得挑选，建议无脑Ubuntu，使用指令```wsl --install -d Ubuntu```即可
![step4](https://images-ave.oss-rg-china-mainland.aliyuncs.com/step4.png)

在Ubuntu安装完毕后，分为两种情况，如果你的WSL版本是WSL2，那么请跳过接下来的步骤，如果不是，请按照下列步骤升级WSL版本
>WSL2相较于WSL1增加了对于完整Linux内核的支持，而docker的运行依赖完整的Linux内核，所以需要升级到WSL2，使用```wsl -l -v```来查看WSL版本

若你的版本为1，请使用以下应用程序进行升级[点击这里下载WSL更新](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi)

下载好后打开安装即可，在安装完成后，以管理员权限打开Powershell，输入```dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart```
在一切部署完毕之后，进入cmd，输入```wsl --set-default-version 2```即可完成升级

随后，我们打开docker安装包，直接安装即可
![step5](https://images-ave.oss-rg-china-mainland.aliyuncs.com/step5.png)
随后重启即可
### 2.安装ollama
ollama的安装则简单许多，在ollama官网下载对应的安装包，并且安装即可
![step6](https://images-ave.oss-rg-china-mainland.aliyuncs.com/step6.png)

在安装完毕之后，我们来到ollama的官网，看看自己想要什么模型
![step7](https://images-ave.oss-rg-china-mainland.aliyuncs.com/step7.png)
这里选择的是qwen2:7b的模型，这里的7b指参数量，参数量越高，性能越强，与此同时需要更强的硬件支持。

直接复制指令到CMD中即可自动下载并部署模型
![step8](https://images-ave.oss-rg-china-mainland.aliyuncs.com/step8.png)

随后即可开始下载
![step9](https://images-ave.oss-rg-china-mainland.aliyuncs.com/step9.png)

下载完后，会进行自动部署，直到你在CMD中看到
![step10](https://images-ave.oss-rg-china-mainland.aliyuncs.com/step10.png)
这样就说明模型的部署已经完成了
### 3.安装maxkb
关于maxkb，你可以直接使用官网的一键安装脚本
>docker run -d --name=maxkb -p 8080:8080 -v ~/.maxkb:/var/lib/postgresql/data cr2.fit2cloud.com/1panel/maxkb

在首次运行后，请关闭这个默认部署的容器，并且删掉容器，保留镜像

因为没有使用本地的保存路径，所以你的maxkb设置和配置将会在重启时丢失，所以，请配置到本地

>docker run -d --name=maxkb -p 8080:8080 -v D:/MaxKB:/var/lib/postgresql/data --privileged=true 1panel/maxkb

使用上述指令是将MAXKB的配置文件保存在本地的D盘，当然，可以根据自己实际情况修改盘符，但在运行前，请删除已有的maxkb容器，或者为该容器重命名

## 三，开始具体部署
首先启动容器，使用浏览器访问127.0.0.1:8080即可进入maxkkb
>默认用户名admin，默认密码MaxKB@123..

然后启动ollama服务，在CMD中输入```ollama serve```即可启动监听，如果出现异常，请检查环境变量

右键此电脑，点击属性，找到高级系统设置，环境变量
![step11](https://images-ave.oss-rg-china-mainland.aliyuncs.com/step11.png)
![step12](https://images-ave.oss-rg-china-mainland.aliyuncs.com/step12.png)
然后点击下方的新建

内容如图所示
![step13](https://images-ave.oss-rg-china-mainland.aliyuncs.com/step13.png)

创建完成后，重启CMD和ollama即可完成配置
---
我们进入maxkb，点击系统设置，模型设置
![step14](https://images-ave.oss-rg-china-mainland.aliyuncs.com/step14.png)

在左边的供应商选择ollama，点击添加模型
![step15](https://images-ave.oss-rg-china-mainland.aliyuncs.com/step15.png)
在模型设置中填写具体的数据
![step16](https://images-ave.oss-rg-china-mainland.aliyuncs.com/step16.png)
如果没有你下载的模型，请直接输入模型名:参数量

例如这里直接输入qwen2:7b

API域名，是你的本机IP:11434

本机IP的查看方式：打开CMD，输入ipconfig，其中IPV4地址那一栏就是你的IP地址
![step17](https://images-ave.oss-rg-china-mainland.aliyuncs.com/step17.png)

至于APIkey，随便填即可，ollama没有APIkey，但是不可为空

随后maxkb就会自动下载模型，下载完成后即可使用，如果你之前下载过了，则不需要重复下载
![step18](https://images-ave.oss-rg-china-mainland.aliyuncs.com/step18.png)
---
随后来到知识库

知识库，相当于对于模型回答的补充，你也可以理解为外挂了一些训练数据，到时候可以直接调用知识库的数据来回答你的问题

![step19](https://images-ave.oss-rg-china-mainland.aliyuncs.com/step19.png)
你可以使用文档，也可以使用网页来构建知识库内容，此处选择网页，并且以我的博客进行例子
![step20](https://images-ave.oss-rg-china-mainland.aliyuncs.com/step20.png)

配置好后点击完成即可

系统会自动分割文本
![step21](https://images-ave.oss-rg-china-mainland.aliyuncs.com/step21.png)
---
# 写不动了，下次写



