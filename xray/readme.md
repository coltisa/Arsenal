### [X-RAY](https://github.com/chaitin/xray)

[![GitHub stars](https://img.shields.io/github/stars/chaitin/xray.svg)](https://img.shields.io/github/stars/chaitin/xray)

说明：一款功能强大的安全评估工具

功能：XSS检测、SQL注入、命令/代码注入检测、目录枚举、弱口令检测



使用说明

说明：以下示例xray的运行文件已改为xray



主动扫描

```
./xray webscan --url https://www.test.com --html-output test.com.html
```



```
./xray webscan --basic-crawler https://www.test.com --html-output test.com.html
```

--basic-crawler比--url更深度，能够包含--url

扫描Pikachu靶站结果示例：



被动扫描

即代理扫描



```
./xray genca
```

生成CA证书后可以直接将其安装到系统中



第一次启动 xray 之后，当前目录会生成 `config.yml` 文件，选择文件编辑器打开，并按照下方说明修改。

在`mitm` 下的 `restriction` 下的 `hostname_allowed` 增加 `test.com`即被测主机地址

因为我们的测试目标站就是 `http://test.com`，增加这个过滤之后，xray 将只会扫描该站的流量，避免扫描到非授权目标站点。



```
./xray webscan --listen 127.0.0.1:7777 --html-output test.proxy.html
```

开启代理后到目标网站点点点，随意输入访问页面即可



服务扫描

目前有自带的PoC如Tomcat的RCE漏洞



还有其它自定义PoC扫描的用法待研究



参考链接

官方说明

https://docs.xray.cool/#/README