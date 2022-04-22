



## NMAP使用说明



### 扫描示例

扫描目标指定端口范围
```bash
nmap -p 50-80 10.0.0.55
```


指定端口扫描
```bash
nmap -p 80,443,801 10.0.0.55
```


路由跟踪
```bash
nmap –traceroute 10.0.0.55
```


设置扫描一个网段下的IP
```bash
nmap -sP 10.1.1.0 /24
```

查看本机开放的端口
```bash
nmap localhost
```

探测主机操作系统类型
```bash
nmap -O 192.168.21.163
Nmap -A 192.168.36.2
```

端口开启的结果示例
```bash
Starting Nmap 6.40 ( http://nmap.org ) at 2020-06-05 18:02 CST
Nmap scan report for 192.168.36.1
Host is up (0.00018s latency).
PORT    STATE         SERVICE
500/udp open|filtered isakmp
MAC Address: 00:50:56:C0:00:08 (VMware)

Nmap done: 1 IP address (1 host up) scanned in 0.55 seconds
```
提示：NMAP实际使用过程中扫描的结果不一定准确

快速扫描IP地址段
```bash
nmap -sS -Pn -n --open --min-hostgroup 4 --min-parallelism 1024 --host-timeout 30 -T4 -v -oG result.txt -iL ip.txt
```



Telnet端口使用Script和字典爆破

```
nmap -p 23 -Pn --script=telnet-brute --script-args=userdb=admin.lst,passdb=passwords.lst,telnet-brute.timeout=3s 10.10.10.10
```

HTTP认证爆破

```
nmap --script=http-brute dvwa.vuln.leafsec.com
```

查看Scripts数量

```
root@kali:~# ls /usr/share/nmap/scripts/ | wc -l
```




扫描UDP端口，UDP端口测试的话还可以使用NC但是还需要在目标服务器上部署服务

```bash
nmap -sU -p 500 192.168.36.1
```



### 参数说明

| 参数                       | 说明                                                         |
| -------------------------- | ------------------------------------------------------------ |
| -v                         | 打印详细扫描过程                                             |
| -sS                        | 使用SYN方式扫描，默认用的是-sT方式，即TCP方式，需要完成完整的三次握手，比较费时，SYN就比较快一些了 |
| -Pn                        | 禁用PING检测，这样速度快，并且可以防止有些主机无法ping通而被漏掉不扫描 |
| -T4                        | 总共有T0-T5，貌似T4比较折中                                  |
| -oG                        | 输出为比较人性化的格式，一条记录一行，后期好处理             |
| -iL                        | 载入IP段文件，批量扫，不用一条条执行了                       |
| --open                     | 只输出检测状态为open的端口，即开放的端口                     |
| --min-hostgroup 4          | 调整并行扫描组的大小                                         |
| --min-parallelism 1024     | 调整探测报文的并行度                                         |
| --host-timeout 30          | 检测超时的跳过                                               |
| --script=script_name       | 指定脚本扫描                                                 |
| --script-args=k1=v1,k2=v2  | 传递脚本里面的参数                                           |
| --script-trace             | 设置该参数，则显示所有的脚本收发请求过程                     |
| –script-args-file=filename | 使用文件为脚本提供参数                                       |
| --auth                     | 负责处理鉴权证书（绕开鉴权）的脚本                           |
| --broadcast                | 在局域网内探查更多服务开启状况，如DHCP/DNS/SQL Server等服务  |
| --brute                    | 供暴力破解方式，针对常见的应用如HTTP/SNMP等                  |
| --default                  | 使用-sC或-A选项扫描时候默认的脚本，提供基本脚本扫描能力      |
| --discovery                | 对网络进行更多的信息，如SMB枚举、SNMP查询等                  |
| --dos                      | 用于进行拒绝服务攻击                                         |
| --exploit                  | 利用已知的漏洞入侵系统                                       |
| --external                 | 利用第三方的数据库或资源，例如进行whois解析                  |
| --fuzzer                   | 模糊测试的脚本，发送异常的包到目标机，探测出潜在漏洞         |
| --intrusive                | 入侵性的脚本，此类脚本可能引发对方的IDS/IPS的记录或屏蔽      |
| --malware                  | 探测目标机是否感染了病毒、开启了后门等信息                   |
| --safe                     | 此类与intrusive相反，属于安全性脚本                          |
| --version                  | 负责增强服务与版本扫描（Version Detection）功能的脚本        |
| --vuln                     | 负责检查目标机是否有常见的漏洞，如是否有MS08_067             |





## 参考链接

权限绕过

https://nmap.org/nsedoc/categories/auth.html

版本检测

https://nmap.org/nsedoc/categories/version.html

恶意软件

https://nmap.org/nsedoc/categories/malware.html

DOS攻击

https://nmap.org/nsedoc/categories/dos.html