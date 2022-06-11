安全项目收集，在此处收集一些Github以及其他开源项目

Tips：很多都是Star中的，可以去我的Star里面看看

# 安全扫描工具

## [XRAY](https://github.com/chaitin/xray)

[![GitHub stars](https://img.shields.io/github/stars/chaitin/xray.svg)](https://img.shields.io/github/stars/chaitin/xray)

说明：一款功能强大的安全评估工具

功能：XSS检测、SQL注入、命令/代码注入检测、目录枚举、弱口令检测

[详情](https://github.com/coltisa/security_collection/tree/main/xray)

## [RAD](https://github.com/chaitin/rad)

说明：Rad主要是可以通过爬取网站的URL，泛洪辐射到全站，从一个URL开始，辐射到一整个站点空间，一款专为安全扫描而生的浏览器爬虫，也是长亭的可以配合XRAY使用

[![GitHub stars](https://img.shields.io/github/stars/chaitin/rad.svg)]()



## [Nuclei](https://github.com/projectdiscovery/nuclei)

[![GitHub stars](https://img.shields.io/github/stars/projectdiscovery/nuclei.svg)](https://img.shields.io/github/stars/chaitin/nuclei)

Kali安装

```
apt install nuclei -y
```

批量扫描

```
nuclei -list urls.txt
```

[详情](https://github.com/coltisa/security_collection/tree/main/nuclei)



## [Ary](https://github.com/TeraSecTeam/ary)

[![GitHub stars](https://img.shields.io/github/stars/TeraSecTeam/ary.svg)]()

说明：多种扫描工具的集成。Ary 是一个集成类工具，主要用于调用各种安全工具，从而形成便捷的一键式渗透。

**目前在CentOS上用不了，待作者更新[2022年3月17日]**

报错：[2002] Failed to execute script ary

## [OneDragon](https://github.com/possib1e/OneDragon)

[![GitHub stars](https://img.shields.io/github/stars/possib1e/OneDragon.svg)]()

说明：多种扫描工具的集成，一键化漏洞扫描。全自动化挖洞，助力挖SRC的赏金猎人白帽子，一键实现子域名扫描，全端口扫描，目录扫描，漏洞扫描。

**目前在CentOS上用不了，待作者更新[2022年3月17日]**

报错：ModuleNotFoundError: No module named 'config.setting'

## [ESD](https://github.com/FeeiCN/ESD)

Enumeration Sub Domain 子域名扫描工具

[![GitHub stars](https://img.shields.io/github/stars/FeeiCN/ESD.svg)]()

说明：简洁好用

![github_security_collection_esd](https://www.miacraft.cn/public/2022/03/20/github_security_collection_esd.png)

## [Goby](https://cn.gobies.org/)

说明：是一款快速梳理资产暴露攻击面的情报挖掘扫描工具，即“网络空间测绘”。可以用来自动爬取子域名、二级域名字典爆破、关联域名查询、支持连接FOFA、XRAY插件、扩大数据源、自定义PoC等

食用指南：https://www.freebuf.com/articles/web/245845.html

## [Nikto](https://github.com/sullo/nikto)

[![GitHub stars](https://img.shields.io/github/stars/sullo/nikto.svg)]()

说明：Nikto是一款开源的（GPL）网页服务器扫描器，它可以对网页服务器进行全面的多种扫描，可以读出服务版本信息、PHP信息等。Kali集成该工具。

## Nessus

说明：一款综合漏洞扫描工具。

## AWVS

说明：是一个自动化的Web应用程序安全测试工具，它可以扫描任何可通过Web浏览器访问的和遵循HTTP/HTTPS规则的Web站点和Web应用程序。可以录制操作动作针对登录后的站点进行逻辑遍历。

| 功能                  | 描述                                            |
| --------------------- | ----------------------------------------------- |
| WebScanner            | 核心功能，安全漏洞扫描                          |
| Site Crawler          | 站点爬行，遍历站点目录结构                      |
| Target Finder         | 主机发现，找出给定网段中开启了80和443端口的主机 |
| Subdomian Scanner     | 子域名扫描器，利用DNS查询                       |
| Blind SQL Injector    | 盲注工具                                        |
| HTTP Editor           | 协议数据包编辑器                                |
| HTTP Sniffer          | HTTP协议嗅探器                                  |
| HTTP Fuzzer           | 模糊测试工具                                    |
| Authentication Tester | Web认证破解工具                                 |

[详情](https://github.com/coltisa/Security_Collection/tree/main/awvs)



## Netsparker

设置内部代理：[Netsparker Standard 内部代理_「Netsparker Standard 中文汉化使用教程」 - 网安](https://www.wangan.com/docs/625)



可以进行动态登录扫描，需要以管理员身份运行

[Netsparker Standard 教程](https://www.wangan.com/docs/628)





## AppScan

## [NMAP](https://github.com/nmap/nmap)

[![GitHub stars](https://img.shields.io/github/stars/nmap/nmap.svg)]()

说明：主机扫描，脚本扫描，隐蔽扫描，端口扫描，服务识别，OS识别，探测WAF

[详情](https://github.com/coltisa/security_collection/tree/main/nmap)

## [Arachni](https://github.com/cmcmsec/arachni)

Web Application Security Scanner Framework

[![GitHub stars](https://img.shields.io/github/stars/cmcmsec/arachni.svg)]()

说明：Web漏洞扫描工具，可以扫描XSS、SQL注入等漏洞

Arachni - Web User Interface

UI: https://github.com/cmcmsec/arachni-ui-web

## [InfoScripts](https://github.com/fatmo666/InfoScripts)

[![GitHub stars](https://img.shields.io/github/stars/fatmo666/InfoScripts.svg)]()

说明：渗透测试/SRC挖掘中用于信息收集的脚本集合，存活主机探测：HostUpCheck.py、HTTP-header信息收集：HeaderCheck.py、CDN探测：CDNCheck.py、CDN绕过：CDNByPass.py、C段扫描：CWebScanner.py、目录爆破：DirBruter.py、整站爬虫：Crawler.py、phpinfo信息收集、分析：PhpInfoCheck.py、端口扫描：PortScanner.py、旁站查询：OtherSiteSearcher.py

## [TotalPass](https://github.com/0xHJK/TotalPass)

[![GitHub stars](https://img.shields.io/github/stars/0xHJK/TotalPass.svg)]()

说明：扫描目标设备是否存在默认密码，搜索常见设备默认密码，支持手动和自动更新密码库。目前支持的设备类型：SSH、Telnet、SNMP、Redis

## [FFUF](https://github.com/ffuf/ffuf)

[![GitHub stars](https://img.shields.io/github/stars/ffuf/ffuf.svg)]()

说明：进行目录爆破扫描，GET、POST参数爆破

Kali环境示例命令，常规目录扫描

```
ffuf -u https://target.cn/FUZZ -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -t 2000 -c
```

模拟GET参数请求，将FUZZ关键字定义为URL的一部分。假设无效的GET参数名响应为4242字节，将其过滤

```
ffuf -w /path/to/paramnames.txt -u https://target/script.php?FUZZ=value -fs 4242
```

模拟GET参数请求，参数名已知，值未知。假设响应代码401为参数值错误，将其过滤

```
ffuf -w /path/to/values.txt -u https://target/script.php?valid_name=FUZZ -fc 401
```

模拟POST请求，过滤掉401的返回代码

```
ffuf -w /path/to/postdata.txt -X POST -d "username=admin\&password=FUZZ" https://target/login.php -fc 401
```

| 常用参数         | 说明                              |
| ------------ | ------------------------------- |
| -u           | 指定URL                           |
| -w           | 指定字典文件                          |
| -t int       | 并发线程数量，默认40                     |
| -c           | 带颜色输出                           |
| -H           | 指定Header，"Name: Value"，可以多个-H参数 |
| -s           | 安静模式，不打印额外信息                    |
| -x           | HTTP Proxy URL                  |
| -r           | 跟随重定向                           |
| -o string    | 输出到文件                           |
| -of string   | 输出文件格式，json, csv, ecsv，默认json   |
| -timeout int | 请求超时时间，默认10s                    |
| -fs string   | 过滤HTTP回复的大小，过滤掉设置值              |
| -fc string   | 过滤请求响应代码，过滤掉设置值                 |

## [WFuzz](https://github.com/xmendez/wfuzz)

[![GitHub stars](https://img.shields.io/github/stars/xmendez/wfuzz.svg)]()

说明：目录爆破

基本使用，目录爆破，根据字典过滤404响应，对目标URL进行爆破，FUZZ指代爆破部分

```
wfuzz -w wordlist/general/common.txt --hc 404 http://testphp.vulnweb.com/FUZZ
```
递归，递归层级为4
```
wfuzz -w big.txt -R 4 --hc 404 http://example.com/FUZZ 

```
保存结果

```
 wfuzz -f outfile,json -w wordlist URL/FUZZ
```



安装参考，Python环境直接PIP安装（需要找到对应的版本）

```
pip install wfuzz
```

使用参考：https://wfuzz.readthedocs.io/en/latest/

## [linglong](https://github.com/awake1t/linglong)

[![GitHub stars](https://img.shields.io/github/stars/awake1t/linglong.svg)]()

说明：实测扫描扫出的东西有限，其就是XRAY主动扫描。甲方资产巡航扫描系统。系统定位是发现资产，进行端口爆破。帮助企业更快发现弱口令问题。主要功能包括: 资产探测、端口爆破、定时任务、管理后台识别、报表展示

![](https://github.com/awake1t/linglong/raw/master/img/index.gif)



## [XSStrike](https://github.com/s0md3v/XSStrike)

[![GitHub stars](https://img.shields.io/github/stars/s0md3v/XSStrike.svg)]()

XSS测试工具



# 其它工具

## [Proxies](https://github.com/0xHJK/Proxies)

[![GitHub stars](https://img.shields.io/github/stars/0xHJK/Proxies.svg)]()

说明：100行Python代码快速获得一个代理池，两分钟获得数千个有效代理

## [BerylEnigma](https://github.com/ffffffff0x/BerylEnigma)

[![GitHub stars](https://img.shields.io/github/stars/ffffffff0x/BerylEnigma.svg)]()

说明：一个CTF+渗透测试工具包，主要实现一些常用的加密与编码功能，在软件使用过程中发现问题或建议欢迎提交 issue,也欢迎提交新功能需求。

## [Penetration](https://github.com/saucer-man/penetration-script)-Script

一些渗透测试常用的小脚本

[![GitHub stars](https://img.shields.io/github/stars/saucer-man/penetration-script.svg)]()

功能：爬取免费代理、爬取全国高校域名、端口扫描(python-nmap)、信息泄露扫描(备份文件、GIT、SVN等)、SQL盲注框架、未授权服务扫描、递归爬取某链接中的URL、PHP随机亦或生成某关键字、域名批量转ip、根据网段生成IP列表、内外方面探测开放端口、基于Selenium的登录爆破脚本、子域名相关：子域名爆破、基于各大在线网站的子域名收集脚本、从URL中解析出顶级域名、补天公益爬虫

## [name-fuzz](https://github.com/ffffffff0x/name-fuzz)

[![GitHub stars](https://img.shields.io/github/stars/ffffffff0x/name-fuzz.svg)]()

说明：针对目标已知信息的字典生成工具。攻击者收集工号、邮箱名，或者直接生成用户名字典进行爆破，成功率非常高

## [MobSF](https://github.com/MobSF/Mobile-Security-Framework-MobSF)

[![GitHub stars](https://img.shields.io/github/stars/MobSF/Mobile-Security-Framework-MobSF.svg)]()

说明：移动安全检测平台Mobile-Security-Framework。Mobile Security Framework (MobSF) is an automated, all-in-one mobile application (Android/iOS/Windows) pen-testing, malware analysis and security assessment framework capable of performing

Mobile Security Framework 是一个自动化的移动App安全测试工具，支持Android和iOS双平台，能够进行静态、动态分析以及Web API测试。MobSF经常被用来对Android或iOS app进行快速安全分析，支持二进制APK&IPA形式以及源代码的zip压缩包。
MobSF支持静态和动态分析。

静态分析，可以对Android、iOS和Windows端移动应用进行快速高效的安全分析，分析组件漏送、协议漏洞、API漏洞等，可以对压缩包内的源代码进行安全审计；动态分析，主要进行中间人攻击漏洞、协议安全、恶意URL的分析；
动态分析，主要对App的交互进行抓包分析。

## [ShiroScan](https://github.com/sv3nbeast/ShiroScan)

[![GitHub stars](https://img.shields.io/github/stars/sv3nbeast/ShiroScan.svg)]()

说明：Shiro<=1.2.4反序列化，一键检测工具

## [Sherlock](https://github.com/sherlock-project/sherlock)

[![GitHub stars](https://img.shields.io/github/stars/sherlock-project/sherlock.svg)]()

说明：根据用户名寻找社交账号。Hunt down social media accounts by username across [social networks](https://github.com/sherlock-project/sherlock/blob/master/sites.md)

## [DefaultCreds-cheat-sheet](https://github.com/ihebski/DefaultCreds-cheat-sheet)

[![GitHub stars](https://img.shields.io/github/stars/ihebski/DefaultCreds-cheat-sheet.svg)]()

说明：各种厂商默认密码表。One place for all the default credentials to assist the Blue/Red teamers activities on finding devices with default password

## [YaKit](https://github.com/yaklang/yakit)

[![GitHub stars](https://img.shields.io/github/stars/yaklang/yakit.svg)]()

说明：国产版的BurpSuite类似工具。MITM实现BurpSuite的国产化替代、PoC/Exp的超集，通过GUI快速对目标进行漏洞探测、史上最强的插件系统设计，你想要的应有尽有、Yak Cloud IDE：内置智能提示的Yak语言云IDE、原生支持的内网穿透，横向漏洞测试效率大增、不依赖Java环境即可原生测试Java类

部署说明：https://www.yaklang.io/docs/startup/

使用说明：https://mp.weixin.qq.com/s?__biz=MzI4NTcxMjQ1MA==&mid=2247554048&idx=1&sn=56ec20ad3a1614e714002509aaba806b

## [OpenCTI](https://github.com/OpenCTI-Platform/opencti)

[![GitHub stars](https://img.shields.io/github/stars/OpenCTI-Platform/opencti.svg)]()

说明：OpenCTI 即 Open Cyber Threat Intelligence Platform，开源网络威胁情报平台。它的创建是为了构建、存储、组织和可视化有关网络威胁的技术和非技术信息。它使用基于 STIX 2 标准的知识模式来执行数据的结构化。并被设计为现代 Web 应用程序，包括 GraphQL API 和面向 UX的前端。此外，OpenCTI 可以与其他工具和应用程序集成，如 MISP、TheHive、MITRE ATT&CK 等

说明参考：https://mp.weixin.qq.com/s?__biz=MzUyMTE0MDQ0OA==&mid=2247491498&idx=1&sn=c2f33f7c09690786fe50dc9d6efe17a4

## [AppInfoScanner](https://github.com/cqkenuo/AppInfoScanner)

[![GitHub stars](https://img.shields.io/github/stars/cqkenuo/AppInfoScanner.svg)]()

一款适用于(Android、iOS、WEB、H5、静态网站)，信息检索的工具，可以帮助渗透测试人员快速获取App或者WEB中的有用资产信息





## 目录扫描工具

## 浏览器插件

### ModHeader

说明：增加浏览器请求参数的插件

### SwitchOmega

说明：浏览器代理插件，支持Sock4\5、HTTP协议

## Dirbuster

说明：目录扫描工具。已集成到Kali中。

Kali用法

```
dirbruster
```

图形化界面设置

首先设置目标地址，其次设置字典，路径位于 `/usr/share/dirbuster/wordlists/directory-list-1.0.txt` ，可以执行标准地探测Standard start point和URL Fuzz，设置Fuzz路径扫描 `/admin/{dir}/`

参考：https://blog.csdn.net/weixin_41489908/article/details/115434107

# 社会工程学

## [Mailget](https://github.com/Ridter/Mailget)

[![GitHub stars](https://img.shields.io/github/stars/Ridter/Mailget.svg)]()

说明：通过脉脉用户猜测企业邮箱

# 信息泄露扫描

扫描Github等平台关键字的项目

## [VIPKID GITHUB MONITOR](https://github.com/VKSRC/Github-Monitor)

[![GitHub stars](https://img.shields.io/github/stars/VKSRC/Github-Monitor.svg)](https://img.shields.io/github/stars/VKSRC/Github-Monitor)

说明：代码泄露扫描，支持Docker-Compose部署。VIPKID安全研发团队打造的用于监控Github代码仓库的系统。

![](https://github.com/VKSRC/Github-Monitor/raw/master/docs/media/screenshot.jpg)

## [CODE6](https://github.com/4x99/code6)

[![GitHub stars](https://img.shields.io/github/stars/4x99/code6.svg)](https://img.shields.io/github/forks/4x99/code6)

[![forks](https://img.shields.io/github/forks/4x99/code6)](https://img.shields.io/github/forks/4x99/code6)

说明：页面简洁，部署简单。码小六是一款 GitHub 代码泄露监控系统，通过定期扫描 GitHub 发现代码泄露行为，为企业安全保驾护航！

![](https://camo.githubusercontent.com/ee5f098462466d25f796af02ca5c48715c1ed6cfb04874389bbedcd390e1b3d3/68747470733a2f2f347839392e6769746875622e696f2f736e617073686f742f636f6465362f686f6d652e706e67)

## [Github leaked patrol](https://github.com/MiSecurity/x-patrol)

[![GitHub stars](https://img.shields.io/github/stars/MiSecurity/x-patrol.svg)](https://img.shields.io/github/stars/MiSecurity/x-patrol)

说明：小米的代码泄露扫描。Github Leaked Patrol为一款Github泄露巡航工具，提供了WEB管理端，后台数据库支持SQLITE3、MYSQL和POSTGRES

## [GShark](https://github.com/madneal/gshark)

[![GitHub stars](https://img.shields.io/github/stars/madneal/gshark.svg)](https://img.shields.io/github/stars/madneal/gshark)

说明：Go语言编写的，需要有Go语言环境。Support multi platform, including Gitlab, Github, Searchcode。

## [Hawkeye](https://github.com/0xbug/Hawkeye)

[![GitHub forks](https://img.shields.io/github/forks/0xbug/Hawkeye.svg)](https://github.com/0xbug/Hawkeye/network)
[![GitHub stars](https://img.shields.io/github/stars/0xbug/Hawkeye.svg)](https://github.com/0xbug/Hawkeye/stargazers)
[![Python 3.x](https://img.shields.io/badge/python-3.x-yellow.svg)](https://www.python.org/) 

说明：监控Github代码库，及时发现员工托管公司代码到GitHub行为并预警，降低代码泄露风险

![](https://user-images.githubusercontent.com/12611275/46849889-0d2d0980-ce24-11e8-832e-35f6f935bf3b.png)

## [GSIL](https://github.com/FeeiCN/GSIL)

[![GitHub stars](https://img.shields.io/github/stars/FeeiCN/GSIL.svg)](https://img.shields.io/github/stars/FeeiCN/GSIL)

GitHub Sensitive Information Leakage

说明：Python开发的，似乎没有图形化界面。Monitor Github sensitive information leaks in near real time and send alert notifications.

## [Dump all](https://github.com/0xHJK/dumpall)

[![GitHub stars](https://img.shields.io/github/stars/0xHJK/dumpall.svg)]()

说明：.git、.svn泄露利用工具。多种泄漏形式，一种利用方式。`.git`源代码泄漏、`.svn`源代码泄漏、`.DS_Store`信息泄漏

# 其它参考信息

## [HackReport](https://github.com/awake1t/HackReport)

[![GitHub stars](https://img.shields.io/github/stars/awake1t/HackReport.svg)]()

说明：本项目在脱敏的情况下整理出常见的报告模板、红蓝对抗技巧、渗透测试方法大全、大型会议PPT

## [Security PPT](https://github.com/FeeiCN/Security-PPT)

[![GitHub stars](https://img.shields.io/github/stars/FeeiCN/Security-PPT.svg)]()

说明：各大安全厂商的技术PPT

## [redteam-tools](https://github.com/r0eXpeR/redteam-tools)

[![GitHub stars](https://img.shields.io/github/stars/r0eXpeR/redteam-tools.svg)]()

说明：红队工具

1.getinfo.sh - 内网信息收集shell脚本

2.httpx.sh - httpx+nuclei批量漏洞探测脚本

3.httpx-url.sh - httpx+nuclei单URL漏洞探测脚本

4.get_title.py - 快速从IP+端口从提取HTTP

5.icohash.sh - 获取icon_hash

## [1earn ](https://github.com/ffffffff0x/1earn)

[![GitHub stars](https://img.shields.io/github/stars/ffffffff0x/1earn.svg)]()

说明：ffffffff0x 团队维护的安全知识框架,内容包括不仅限于 web安全、工控安全、取证、应急、蓝队设施部署、后渗透、Linux安全、各类靶机writup。本项目的初衷是分享知识资源,让更多人接触和了解安全、运维领域,但受限于本人能力有限,难免会有错误和借鉴的地方,对于内容中有疑问或建议请提交 issue.

文章链接：[学习路线](https://github.com/ffffffff0x/1earn/blob/master/roadmap.md)、[JWT安全](https://github.com/ffffffff0x/1earn/blob/master/1earn/Security/RedTeam/Web%E5%AE%89%E5%85%A8/Web_Tricks/JWT%E5%AE%89%E5%85%A8.md)、[工控协议](https://github.com/ffffffff0x/1earn/blob/master/1earn/Security/ICS/%E5%B7%A5%E6%8E%A7%E5%8D%8F%E8%AE%AE.md)

## [Pentest101](https://github.com/ffffffff0x/Pentest101)

[![GitHub stars](https://img.shields.io/github/stars/ffffffff0x/Pentest101.svg)]()

说明：每周分享一些关于渗透测试的知识点，由ffffffff0x 团队维护

## [PenetrationTest-Tips](https://github.com/Power7089/PenetrationTest-Tips)

[![GitHub stars](https://img.shields.io/github/stars/Power7089/PenetrationTest-Tips.svg)]()

说明：渗透测试小技巧，渗透测试Tips

## [Mind-Map](https://github.com/phith0n/Mind-Map)

[![GitHub stars](https://img.shields.io/github/stars/phith0n/Mind-Map.svg)]()

说明：各种安全相关思维导图整理收集

## [红队攻击思维](https://cloud.tencent.com/developer/article/1480895)

说明：各种学习资料，包括攻防测试手册、CheckList、靶场等

## [火线ZONE](https://zone.huoxian.cn/)

说明：各种学习资料，工具、渗透姿势等

## [Vehicle-Security-Toolkit](https://github.com/VulnTotal-Team/Vehicle-Security-Toolkit)

[![GitHub stars](https://img.shields.io/github/stars/VulnTotal-Team/Vehicle-Security-Toolkit.svg)]()

汽车/安卓/固件/代码安全测试工具集



# 防御工具

## [X-WAF](https://github.com/xsec-lab/x-waf)

[![GitHub stars](https://img.shields.io/github/stars/xsec-lab/x-waf.svg)]()

说明：基于Openresty，Lua+NGINX框架。适用于中小企业的云WAF。

## [Lua-Resty-WAF](https://github.com/p0pr0ck5/lua-resty-waf)

[![GitHub stars](https://img.shields.io/github/stars/p0pr0ck5/lua-resty-waf.svg)]()

说明：基于Lua+NGINX框架。High-performance WAF built on the OpenResty stack。

## [NGX_Lua_WAF](https://github.com/loveshell/ngx_lua_waf)

[![GitHub stars](https://img.shields.io/github/stars/loveshell/ngx_lua_waf.svg)]()

说明：基于Lua+NGINX框架。ngx_lua_waf是一个基于lua-nginx-module(openresty)的web应用防火墙。

## [OpenWAF](https://github.com/titansec/OpenWAF)

[![GitHub stars](https://img.shields.io/github/stars/titansec/OpenWAF.svg)]()

说明：基于Lua+NGINX框架。Web security protection system based on openresty。

## [QSNM](https://github.com/iqiyi/qnsm)

[![GitHub stars](https://img.shields.io/github/stars/iqiyi/qnsm.svg)]()

说明：QNSM(IQIYI Network Security Monitor) 是一个旁路部署的全流量、实时、高性能网络安全监控引擎，基于DPDK开发，集成了DDoS检测和IDPS模块。IDPS模块基于[Suricata](https://github.com/OISF/suricata)，并新增了一些特性。QNSM is network security monitoring framework based on DPDK.

## [OSSEC-WUI](https://github.com/NunesGodinho/OSSEC-WUI)

[![GitHub stars](https://img.shields.io/github/stars/NunesGodinho/OSSEC-WUI.svg)]()

说明：HIDS OSSEC平台UI

# Wordlist and Dictionary

https://www.invicti.com/blog/web-security/svn-digger-better-lists-for-forced-browsing/

# 靶场与练习

## [Vulhub](https://github.com/vulhub/vulhub)

[![GitHub stars](https://img.shields.io/github/stars/vulhub/vulhub.svg)]()

下载地址：https://www.vulnhub.com/entry/evilbox-one,736/

Vulhub测试说明：https://www.freebuf.com/articles/web/335263.html

## [Pikachu](https://github.com/zhuifengshaonianhanlu/pikachu)

[![GitHub stars](https://img.shields.io/github/stars/zhuifengshaonianhanlu/pikachu.svg)]()

说明：基于PHP，可以使用Docker部署。一个好玩的Web安全-漏洞测试平台

## [TIWAP](https://github.com/tombstoneghost/TIWAP)

[![GitHub stars](https://img.shields.io/github/stars/tombstoneghost/TIWAP.svg)]()

说明：TIWAP是一款包含大量漏洞的Web应用渗透测试学习工具，同时也开始一个Web安全测试平台，该工具基于Python和Flask实现其功能。当前版本的TIWAP实验环境中包含了二十种安全漏洞，具体如下所示：、SQL注入、Blind SQL注入、NoSQL注入、Command注入、业务逻辑漏洞、敏感数据泄露、XML外部实体、安全错误配置、反射型XSS、存储型XSS、基于DOM的XSS、HTML注入、不安全的证书验证、硬编码Credentials、不安全的文件上传、暴力破解、目录遍历、跨站请求伪造(CSRF)、服务器端请求伪造(SSRF)、服务器端模板注入(SSTI)

说明参考：https://mp.weixin.qq.com/s?__biz=MjM5NjA0NjgyMA==&mid=2651154560&idx=4&sn=92d991f201725307b8c8fe339d4ad765



## [IoT-Vulhub](https://github.com/VulnTotal-Team/IoT-vulhub)

[![GitHub stars](https://img.shields.io/github/stars/VulnTotal-Team/IoT-vulhub.svg)]()

受 [Vulhub](https://github.com/vulhub/vulhub) 项目的启发，一个 IoT 版的固件漏洞复现环境，目前有[Cisco/CVE-2020-3331](https://github.com/VulnTotal-Team/IoT-vulhub/tree/master/Cisco/CVE-2020-3331)、[HUAWEI/CVE-2017-17215](https://github.com/VulnTotal-Team/IoT-vulhub/tree/master/HUAWEI/CVE-2017-17215)、[TP-Link](https://github.com/VulnTotal-Team/IoT-vulhub/tree/master/TP-Link) 等漏洞复现环境





## Hack The Box

靶场渗透测试练习平台

https://www.hackthebox.com/universities

[![Hack The Box: Cybersecurity Training](https://www.hackthebox.com/images/logo-htb.svg)](https://www.hackthebox.com/)

使用参考：

https://zhuanlan.zhihu.com/p/98483328

https://www.cnblogs.com/black--horse/p/14705919.html

# 社区与平台

### TOOLS安全导航

[安全站点导航-Backlion整理 - T00ls.Com](https://www.t00ls.cc/navi.html)





### Tide安全团队

https://www.tidesec.com/

#### 文库

包含漏洞武器库、红蓝对抗、免杀、移动安全、IoT物联网、代码审计、工控、应急响应、社工钓鱼、测试用例

http://wiki.tidesec.com/

远控免杀 Wiki
http://wiki.tidesec.com/docs/bypassav
红蓝对抗 Wiki
http://wiki.tidesec.com/docs/RedTeam
ICS工控安全
http://wiki.tidesec.com/docs/ICS
IoT物联网安全
http://wiki.tidesec.com/docs/IoT
APP移动安全
http://wiki.tidesec.com/docs/APP
CobaltStrike
http://wiki.tidesec.com/docs/CobaltStrike
应急响应 Wiki
http://wiki.tidesec.com/docs/Emergency
代码审计 Wiki
http://wiki.tidesec.com/docs/CodeAudit
密码学 Wiki
http://wiki.tidesec.com/docs/Crypto

#### 导航

http://paper.tidesec.com/



参考链接

渗透测试工具库 https://www.bilibili.com/read/cv7778176