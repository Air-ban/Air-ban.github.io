# 前言
onedrive是微软下面一项相当好用的服务，有免费的存储空间，且不限速，但，微软并没有为onedrive提供**Linux客户端**，这就让Linux用户很难绷，以下是一些可以在Linux上使用Onedrive的方法
## 环境说明
操作环境：
- Ubuntu 24.04
### 方法一（推荐）
首先打开系统自带的设置，找到左边的在线账号，如下图所示
![](https://images-ave.oss-rg-china-mainland.aliyuncs.com/%E6%88%AA%E5%9B%BE%202024-08-12%2016-00-49.png)
选择**Microsoft 365**
![](https://images-ave.oss-rg-china-mainland.aliyuncs.com/%E6%88%AA%E5%9B%BE%202024-08-12%2016-03-37.png)
此处无需填写任何项，直接点击下方登陆即可，随后浏览器会跳转到MS官方登陆界面，正常登陆账号即可

![](https://images-ave.oss-rg-china-mainland.aliyuncs.com/%E6%88%AA%E5%9B%BE%202024-08-12%2016-05-12.png)
登陆完成后，打开这个Files的开关，随后就可以在自己的文件中看到这个外部存储器了
![](https://images-ave.oss-rg-china-mainland.aliyuncs.com/%E6%88%AA%E5%9B%BE%202024-08-12%2016-06-28.png)
### 方法二
在linux中安装onedriver客户端，这里以Ubuntu为例，首先安装onedriver客户端，使用如下指令
>sudo add-apt-repository ppa:jstaf/onedriver

>sudo apt update

>sudo apt install onedriver

随后即可在应用程序中找到onedriver，打开后如图所示
![](https://images-ave.oss-rg-china-mainland.aliyuncs.com/%E6%88%AA%E5%9B%BE%202024-08-12%2016-11-09.png)
首先点击左上角，选择一个同步文件夹，这里建议新建一个文件夹，文件夹名字最好使用英文，中文会出现莫名其妙的报错
![](https://images-ave.oss-rg-china-mainland.aliyuncs.com/%E6%88%AA%E5%9B%BE%202024-08-12%2016-14-13.png)
选择好文件夹后，登陆自己的MS账号
![](https://images-ave.oss-rg-china-mainland.aliyuncs.com/%E6%88%AA%E5%9B%BE%202024-08-12%2016-14-40.png)
登陆好后会自动挂载，并启动服务
![](https://images-ave.oss-rg-china-mainland.aliyuncs.com/%E6%88%AA%E5%9B%BE%202024-08-12%2016-15-39.png)
![](https://images-ave.oss-rg-china-mainland.aliyuncs.com/%E6%88%AA%E5%9B%BE%202024-08-12%2016-16-26.png)
可以直接访问，并且会同步文件更改

但是这个方法有一个致命的缺点，如果你需要上传大文件，会非常吃运行内存，直到内存被吃爆，我上传1.2G文件，内存占用5.7G，就，有种无力感
![](https://images-ave.oss-rg-china-mainland.aliyuncs.com/3F62051B011A693CFAC8617137EE1EA8.png)
但这个方法确实是这三种方法里面较快的方法，只针对小文件的修改或者上下传，是非常好的选择

### 方法三
此方法相较于上面两种方法，几乎没有什么额外的优势，但还是可以当作一种方法，在不同的设备上，不想下载onedrive客户端的使用场景，本方法使用webdav来挂载到本地

首先打开[koofr](https://koofr.eu/)，简单注册一个账号，登陆到后台，点击侧边栏的Connect
![](https://images-ave.oss-rg-china-mainland.aliyuncs.com/%E6%88%AA%E5%9B%BE%202024-08-12%2016-23-59.png)
![](https://images-ave.oss-rg-china-mainland.aliyuncs.com/%E6%88%AA%E5%9B%BE%202024-08-12%2016-25-28.png)
选择onedrive，点击**Connect OneDrive**
![](https://images-ave.oss-rg-china-mainland.aliyuncs.com/%E6%88%AA%E5%9B%BE%202024-08-12%2016-26-01.png)
随后还是老样子，登陆自己的MS账号，登陆完成后，会同步，应该是从MS服务器拉文件列表下来，可能需要个五分钟左右

现在我们点击自己头像下面的**Preferences**，进入设置选项
![](https://images-ave.oss-rg-china-mainland.aliyuncs.com/%E6%88%AA%E5%9B%BE%202024-08-12%2016-28-16.png)
点击左侧的**Password**，找到下面的**APP password**
![](https://images-ave.oss-rg-china-mainland.aliyuncs.com/%E6%88%AA%E5%9B%BE%202024-08-12%2016-29-52.png)
随便填个APPname，随后点击**Generate**
![](https://images-ave.oss-rg-china-mainland.aliyuncs.com/%E6%88%AA%E5%9B%BE%202024-08-12%2016-31-44.png)
你会获得一个密码
![](https://images-ave.oss-rg-china-mainland.aliyuncs.com/774445af-3e72-45e0-a7c5-99aa7936446b.png)
记下这个密码，来到Ubuntu的文件管理，点击*其他位置*，在下面的服务器地址输入框输入```davs://app.koofr.net/dav/Koofr```
![](https://images-ave.oss-rg-china-mainland.aliyuncs.com/%E6%88%AA%E5%9B%BE%202024-08-12%2016-34-20.png)
随后点击连接，用户名输入你注册时填写的邮箱，密码是刚刚生成的密码，即可连接

要注意，koofr会有限流机制，每天只有3G的免费流量限额，一旦用过，将无法再通过koofr对onedrive文件进行读写，所以没什么优势，还是建议使用第一种系统内挂载的方法，没什么限制

## The End