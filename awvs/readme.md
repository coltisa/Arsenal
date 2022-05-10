## [AWVS]()



## 使用参考



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

