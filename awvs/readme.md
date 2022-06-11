## [AWVS]()

## 使用参考



点击Targets模块，选择Add Target

![](https://static.miacraft.cn/github/security_collection/awvs/select_target.png)

输入扫描路径参数之后进入到其它设置，可以新建（录制）登录序列脚本

![](https://static.miacraft.cn/github/security_collection/awvs/new_login_record.png)

可以模拟登录一个网站，然后对网站的功能都操作一遍，完成之后点Finish

![](https://static.miacraft.cn/github/security_collection/awvs/after_login.png)



![](https://static.miacraft.cn/github/security_collection/awvs/recorded_lcr.png)

保存之后下次可以直接使用带了登录模拟器的扫描项目

![](https://static.miacraft.cn/github/security_collection/awvs/run_scan.png)





参考链接：https://blog.csdn.net/BlackEnn/article/details/106577619



## 部署参考

### Docker部署

可以先尝试搜索一下 `docker search awvs` 

```
docker pull secfa/docker-awvs
```

```
docker run -d -p 3443:3443 --name awvs secfa/docker-awvs
```

开启/关闭实例

```
docker start awvs
docker stop awvs
```

使用Docker容器地址加3443端口登录即可，即https://hostname:3443/

username: admin@admin.com
password: Admin123

参考链接：https://blog.csdn.net/jcmj123456/article/details/114272715

## 参考链接

其它工具联动姿势

### **[AWVS14-Scan](https://github.com/test502git/awvs14-scan)**
