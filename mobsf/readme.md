## [MobSF](https://github.com/MobSF/Mobile-Security-Framework-MobSF)

[![GitHub stars](https://img.shields.io/github/stars/MobSF/Mobile-Security-Framework-MobSF.svg)]()

说明：移动安全检测平台Mobile-Security-Framework。Mobile Security Framework (MobSF) is an automated, all-in-one mobile application (Android/iOS/Windows) pen-testing, malware analysis and security assessment framework capable of performing

Mobile Security Framework 是一个自动化的移动App安全测试工具，支持Android和iOS双平台，能够进行静态、动态分析以及Web API测试。MobSF经常被用来对Android或iOS app进行快速安全分析，支持二进制APK&IPA形式以及源代码的zip压缩包。
MobSF支持静态和动态分析。

静态分析，可以对Android、iOS和Windows端移动应用进行快速高效的安全分析，分析组件漏送、协议漏洞、API漏洞等，可以对压缩包内的源代码进行安全审计；动态分析，主要进行中间人攻击漏洞、协议安全、恶意URL的分析；
动态分析，主要对App的交互进行抓包分析。



## 部署参考

注意如果要进行动态检测的话不能使用Docker和虚拟机部署，需要使用物理机

### Ubuntu环境部署

部署环境Ubuntu 18.04

\#为保证相关工具包下载顺畅首先更新APT Source

 

先安装Python3-pip等工具

\#可以更改PIP源

```
sudo  apt-get install git
sudo  apt-get install python3-pip
sudo  apt-get install python3-venv
sudo  apt-get install openjdk-8-jre-headless
sudo  apt-get install net-tools
sudo  apt-get install android-tools-adb android-tools-fastboot  
```

从GitHub上克隆MobSF项目，如果下载失败的话可以考虑从本地下载再将zip包上传

```
git clone https://github.com/MobSF/Mobile-Security-Framework-MobSF.git  
```

\#或者下载好包之后直接上传到服务器，并解压

```
unzip  Mobile-Security-Framework-MobSF-master.zip  
```

进入目录运行安装脚本

```
cd Mobile-Security-Framework-MobSF-master  ./setup.sh  
```

\#部分依赖包可能会下载失败，需要多试几次或者从https://pypi.org/下载并手动安装

使用以下命令开启MobSF服务

设置相应命令的环境变量，注意最好使用root账号开启服务

```
source  /MobSF/Mobile-Security-Framework-MobSF-master/venv/bin/activate  
```

开启服务

```
python3 manage.py runserver 0.0.0.0:8000
```

\#可以通过以下命令查看(TCP)端口是否开放起来

```
netstat -ntpl
```

\#注意，由于网络问题，有时候下载依赖包可能会失败，有点组件可能会丢包，可以尝试多次./setup.sh部署

 

\#注意若需要生成PDF报告的话还需要安装wkhtmltopdf工具

\#wkhtmltopdf下载链接#此处需要根据系统下载相应的版本，下载了Ubuntu18.04 amd的版本

https://wkhtmltopdf.org/downloads.html

将包上传到服务器之后进行安装，需要先安装xfonts-75dpi

```
apt  install xfonts-75dpi  dpkg -i  wkhtmltox_0.12.5-1.bionic_amd64.deb   
```

安装完后即可生成PDF报告 



### Windows环境部署 

推荐使用Ubuntu部署，Windows环境无法静态分析IPA

安装Python

找到对应的Python版本，目前2022.4最新版本推荐Python3.8和Python3.9

https://www.python.org/downloads/

安装JDK

https://www.oracle.com/technetwork/java/javase/downloads/jdk13-downloads-5672538.html

 

下载项目文件

可以通过GIT下载或直接下载zip包

*下载安装GIT克隆项目

推荐下载淘宝的

https://github.com/waylau/git-for-win

https://npm.taobao.org/mirrors/git-for-windows/

```
git init

git config http.sslVerify "false"

git clone https://github.com/MobSF/Mobile-Security-Framework-MobSF.git
```

下载项目文件，下载后为.zip包，将其解压后，切换到Mobile-Security-Framework-MobSF目录



可以直接运行setup.bat或者先提前安装相关依赖包

```
python -m pip install -r requirements.txt
```

其中部分模块安装可能会遇到问题，可以手动下载安装，手动安装Python扩展包如

```
Python setup.py install
```

例如google-play-scraper 0.0.1.1的模块，下载后解压进入该目录，使用上面的命令，遇到报错

https://pypi.org/project/google-play-scraper/#files

例如frida需要手动进行安装，且Python3.8对应的frida Windows下只有15.1.14，所以需要手动安装

到PyPi站点https://pypi.org/project/frida/15.1.14/#files下载TAR压缩包，解压后包然后手动安装



 

### 部署参考

https://www.jianshu.com/p/4ba4312985ee

https://www.jianshu.com/p/273c34b05f14

https://testerhome.com/topics/11293

官方说明参考

https://github.com/MobSF/Mobile-Security-Framework-MobSF/wiki/1.-Documentation

https://mobsf.github.io/docs/#/zh-cn/



## 使用说明

如果结果需要PDF版本则需要安装PDF，Windows环境还需要设置环境变量

参考https://github.com/JazzCore/python-pdfkit/wiki/Installing-wkhtmltopdf



### 静态测试

将APK和IPA直接扔进页面即可



### 动态测试

**Android 5.0 - 10.0** -这些版本使用 **Frida**，开箱即用，无需设置

**Android 4.1 - 4.4** - 这些版本使用 **Xposed Framework** 并要求您在首次进行Dynamic Analysis之前先移动运行时。这些版本还要求在安装Xposed模块后重新引导VM。



新增ADB系统环境变量以及在<user_home_dir>/.MobSF/config.py中增加ADB的路径

```
ADB_BINARY = 'D:/Windows10/platform-tools/adb.exe'
```

如果系统不能连接Github则需要提前下载到frida server android`<user_home_dir>/.MobSF/downloads`目录

https://github.com/frida/frida/releases



#### Genymotion对接

[已成功测试]

环境信息

Ubuntu 18.04 可上网，最好更改APT安装源

Genymotion&VirtualBox，推荐使用Genymotion对接，使用其他模拟器对接会有adb命令错误

\#Genymotion首先需要注册账号才能下载

下载链接：

https://www.genymotion.com/download/

\#建议下载带有VirtualBox版本的，直接捆绑VirtualBox安装

安装好后选择相应手机和系统版本发虚机，其Android虚机其实是在VirtualBox中运行

在MobSF虚机中先安装ADB和mitmproxy

```
sudo  apt-get install android-tools-adb android-tools-fastboot  sudo  apt-get install mitmproxy  
```

MobSF也配置好相应的IP和端口

配置MobSF/settings.py的参数

```python
ANALYZER_IDENTIFIER  = '192.168.200.35:5555'  
```

\#注意VirtualBox和Genymotion中可以都将网卡设置为桥接模式

设置相应命令的环境变量

```
source  /MobSF/Mobile-Security-Framework-MobSF-master/venv/bin/activate  
```

配置完后开启MobSF服务，进入动态测试页面即可开始测试

```
python3 manage.py runserver 0.0.0.0:8081  
```

 

Genymotion安装教程：

https://blog.csdn.net/yht2004123/article/details/80146989



#### VMware模拟Android虚机对接

利用VMware安装安卓虚拟机并进行对接，此方式可能需要安装mitmdump

先安装ADB和mitmproxy

```
sudo  apt-get install android-tools-adb android-tools-fastboot  sudo  apt-get install mitmproxy  
```

配置Vmware Android虚拟参考：[VMware Workstation安装安卓虚拟机](https://blog.miacraft.cn/index.php/archives/136/)

将VMware虚机网络配置为桥接模式，则其可获取到主机相同段IP

使用其虚拟机中的终端模拟器，输入ip add命令即可查看其IP

![](https://raw.githubusercontent.com/coltisa/security_collection/main/mobsf/simulator_terminal.png)

配置MobSF/settings.py的参数，其中IP即为Android虚机的IP

```
ANALYZER_IDENTIFIER  = '192.168.200.35:5555'  
```

配置完后开启MobSF服务，进入动态测试页面即可开始测试

```
python3 manage.py runserver 0.0.0.0:8081
```



#### 夜神模拟器对接

先安装ADB

```
sudo  apt-get install android-tools-adb android-tools-fastboot  
```

\#由于夜神模拟器为Android5不能使用XPosed等测试，最好使用Android5以上的版本

配置好MobSF之后，需要对应搭配Android测试环境，此处我们选择夜神模拟器

从官网下载夜神模拟器后，设置其网络配置，开启其网络桥接功能，如下图所示，配置完成后会要求重启

![](https://raw.githubusercontent.com/coltisa/security_collection/main/mobsf/nox_net_setting.png)



*旧版本中在项目目录中配置MobSF/settings.py的参数

```
ANALYZER_IDENTIFIER = '192.168.200.35:5555'
```

新版本中v3.5 beta中需要到`<user_home_dir>/.MobSF/config.py`路径配置ANALYZER_IDENTIFIER参数

```
ANALYZER_IDENTIFIER = '192.168.200.35:5555'
```

修改配置后再执行一次setup.bat/setup.sh，注意可能会检测更新，而更新站点为Github所以最好设置加速

```
setup.sh
```

配置完后开启MobSF服务，进入动态测试页面即可开始测试

使用run.bat/setup.sh开启MobSF服务

```
run.sh
```

*旧版本中使用以下命令

```
python3 manage.py runserver 0.0.0.0:8081  
```



### Troubleshooting





### 使用参考

https://www.jianshu.com/p/f715d3c6a1c7

 

## 参考链接

MobSF教程

https://testerhome.com/topics/11293

源码以及原理解析

[http://purpleroc.com/MD/2016-08-31@Android%20Malware%20Analysis%20Tool(1)--MobSF.html](http://purpleroc.com/MD/2016-08-31@Android Malware Analysis Tool(1)--MobSF.html)

 



