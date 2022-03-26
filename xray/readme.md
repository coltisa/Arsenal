## [XRAY](https://github.com/chaitin/xray)

[![GitHub stars](https://img.shields.io/github/stars/chaitin/xray.svg)](https://img.shields.io/github/stars/chaitin/xray)

说明：一款功能强大的安全评估工具

功能：XSS检测、SQL注入、命令/代码注入检测、目录枚举、弱口令检测



## 使用说明

说明：以下示例xray的运行文件已改为xray

注意：Windows平台使用PowerShell开启



首先可以使用`./xray help`生成config.yml配置文件

### 主动扫描

普通扫描

```
./xray webscan --url https://www.test.com --html-output test.com.html
```

爬虫扫描

```
./xray webscan --basic-crawler https://www.test.com --html-output test.com.html
```

--basic-crawler比--url更深度，能够包含--url

扫描Pikachu靶站结果示例在目录内



### 被动扫描

即代理扫描

1.首先生成CA证书，生成CA证书后可以直接将其安装到系统中

```
./xray genca
```

第一次启动 xray 之后，当前目录会生成 `config.yml` 文件，选择文件编辑器打开，并按照下方说明修改。

在`mitm` 下的 `restriction` 下的 `hostname_allowed` 增加 `test.com`即被测主机地址

因为我们的测试目标站就是 `http://test.com`，增加这个过滤之后，xray 将只会扫描该站的流量，避免扫描到非授权目标站点。

2.开启代理端口

```
./xray webscan --listen 127.0.0.1:7777 --html-output test.proxy.html
```

开启代理后到目标网站点点点，随意输入访问页面即可



### 服务扫描

目前有自带的PoC如Tomcat CVE-2020-1938任意文件读取漏洞

参数配置目前比较简单，输入支持两种方式，快速检测单个目标

```
./xray servicescan --target 127.0.0.1:8009
```

批量检查的 1.file 中的目标, 一行一个目标，带端口

```
./xray servicescan --target-file 1.file 
```

其中 1.file 的格式为一个行一个 service，如

```
10.3.0.203:8009
127.0.0.1:8009
```



### Burp Suite联动

在Burp Suite配置XARY的代理端口即可

![burpsuite_upstream](https://www.miacraft.cn/public/2022/03/21/burpsuite_upstream.png)



### Rad联动



开启XRAY代理模式

```
xray webscan --listen 127.0.0.1:7777 --html-output proxy.html
```

运行Rad

```
rad -t http://example.com -http-proxy 127.0.0.1:7777
```



Rad爬取

基本结果输出示例-text-output

```
GET https://venus.com/
GET https://venus.com/static/map/dmap.min.js
GET https://venus.didachuxing.com/static/map/
GET https://venus.didachuxing.com/static/
```

完整版结果输出示例-full-text-output

```
GET / HTTP/1.1
Host: venus.com
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) HeadlessChrome/99.0.4844.74 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Upgrade-Insecure-Requests: 1
Accept-Encoding: gzip


--------------------------------------------------
GET /static/map/dmap.min.js HTTP/1.1
Host: venus.com
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/87.0.4280.88 Safari/537.36
Accept: */*
Referer: https://venus.didachuxing.com/
Accept-Encoding: gzip
```





https://github.com/ox01024/Xray_Rad_Fusion

https://github.com/chaitin/rad



### Goby联动

https://blog.csdn.net/m0_46699477/article/details/109458757



### 其它联动

联动crawlergo等

https://www.freebuf.com/sectool/252790.html



### 后台执行示例

```
nohup ./xray servicescan --target-file services.list --html-output services.list.html >> run.log 2>&1 &
```



### Reverse 

Reverse平台常用于解决没有回显的漏洞探测的情况，最常见的应该属于SSRF和 存储型XSS

依赖Reverse的漏洞类型SSRF、Struts S2-052、FastJSON（高级版）、XXE、



需要在防火墙上开启UDP 53和指定的HTTP端口



客户端配置，其它保持默认

```
reverse:
  token: "your_token"
  client:
    remote_server: true
    http_base_url: "http://1.1.1.1:80"      
```

服务端配置，其它保持默认

```
reverse:
  db_file_path: "reverse.db"
  token: "your_token"
  http:
  	enabled: true
    listen_ip: 0.0.0.0
    listen_port: "80"
```

在服务端开启Reverse服务

```
./xray reverse
```

客户端直接开启扫描进程即可

```
./xray webscan --basic-crawler https://www.test.com --html-output test.com.html
```



*DNS配置主要用于DNS Rebinding等漏洞，如无特殊需要可以不用配置

https://unit42.paloaltonetworks.com/dns-rebinding/



参考链接

https://docs.xray.cool/#/configration/reverse

https://github.com/gwl7810/xray/blob/master/docs/scenario/reverse_server_ssrf.md

https://blog.csdn.net/xiaofengdada/article/details/122375019









### 插件选择

```
# 漏洞探测的插件配置
# 更多解释见 https://docs.xray.cool/#/configration/plugins
plugins:
  baseline:
    enabled: true
    detect_cors_header_config: true     # 检查 cors 相关配置
    detect_server_error_page: true      # 检查服务器错误信息
    detect_system_path_leak: false      # 检查响应是否包含系统路径泄露
    detect_outdated_ssl_version: false  # 检查 ssl 版本问题
    detect_http_header_config: false    # 检查 http 安全相关 header 是否配置
    detect_cookie_httponly: false       # 检查 set-cookie 时是否设置 http only
    detect_china_id_card_number: false  # 检查响应是否存在身份证号
    detect_china_phone_number: false    # 检查响应是否存在电话号码
    detect_china_bank_card: false       # 检查响应是否存在银行卡号
    detect_private_ip: false            # 检查响应是否包含内网 ip
```

> 通过`enable`开关，决定功能检测是否开启。





另外还有

subdomain 是子域名扫描的命令，仅高级版才有



还有其它自定义PoC扫描的用法待研究



## 参考链接

官方说明文档

https://docs.xray.cool/#/README

高级版破解

https://www.cnblogs.com/cl0ud/p/13884206.html



各种联动

https://www.cnblogs.com/jujuxia/p/15361949.html

https://www.bilibili.com/read/cv12314851