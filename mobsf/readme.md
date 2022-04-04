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



 

### 参考链接

https://www.jianshu.com/p/4ba4312985ee

https://www.jianshu.com/p/273c34b05f14

https://testerhome.com/topics/11293

官方说明参考

https://github.com/MobSF/Mobile-Security-Framework-MobSF/wiki/1.-Documentation

https://mobsf.github.io/docs/#/zh-cn/



## 使用说明



