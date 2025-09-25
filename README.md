# Cake

> 一个功能强大，覆盖全面的集成式红队工具~（亲测很全面）🤔🤔🤔

<img width="2344" height="1464" alt="image" src="https://github.com/user-attachments/assets/45b1818b-7a8b-4075-ab86-36d8ebcdd2c8" />


## 工具简介

> 总结一句话：**把公司名或域名丢对应的文件里面，就可以去恰饭了~**

Cake，发布者：<a href="https://github.com/Bifishone">Bifishone</a>，一个功能强大，覆盖全面的集成式红队工具，涵盖小程序、APP等信息收集、子域名收集、资产测绘、常见CMS/WEB等漏洞检测 (不是nuclei等这种，而是为针对各种漏洞的检测及利用单独写的python检测脚本)、备案/证书/CDN/域名解析IP/IP检测/网站架构检测/邮箱爆破等、端口扫描、指纹识别等众多功能，可实现一键式启动开启全覆盖扫描！(ps：非常适合小白使用🤔🤔🤔~)

## 集成工具

Cake包括LargeCake和LittleCake这两个工具，其中LargeCake的覆盖面比LittleCake更为全面（使用区别很简单🤔🤔😁↓↓↓）

> LargeCake：把公司名称直接放到CompanyName.txt文件中即可！（从公司名称开始进行一系列信息收集工作~）
>
> LittleCake：把子域名放到domain.txt文件中即可！（从子域名开始进行一系列信息收集工作~）

Cake集成了众多Github优秀项目上的常见子域名收集以及资产收集工具（不常见的也有哦~😘），旨在最大程度上做到对资产信息的全面收集，集成的大部分工具与原Github项目略有不同，对大部分工具进行了性能、界面的优化，增加了部分实用功能和参数（具体详情见代码），基本进行了二开优化。

LittleCake比LargeCake多了一个“炫酷小操作”，请自行查看~😘     

### APP、微信小程序、微信公众号、微博等信息收集

> Cake/Collector/AppWechatInfo

- AppWechatInfo (自研脚本) (持续更新研究中……🤔)

### ICP备案

> Cake/Collector/ICPSearch

- ICPSearch（增加代理池、自定义线程、延时爬取等功能）
- ENScan（https://github.com/wgpsec/ENScan_GO）

### 子域名收集

>Cake/Collector/Subdomain

- Subfinder（https://github.com/projectdiscovery/subfinder）
- SubDomainsBrute（https://github.com/lijiejie/subDomainsBrute）
- Subdomain3（https://github.com/yanxiu0614/subdomain3）
- Sublist3r（https://github.com/aboul3la/Sublist3r）
- Findedomain（https://github.com/Findomain/Findomain）
- ksubdomain（https://github.com/knownsec/ksubdomain）
- dnsub（https://github.com/yunxu1/dnsub）
- knock（https://github.com/guelfoweb/knock）

### 资产测绘类收集

> Cake/Collector/ApISearch

- githubSubdomains（推荐挂代理，把自己的Token添加进token.ini）
- OthersApiSubdomains
- SubdomainInterface
- WebSpaceSearchEngine

### 辅助检测

>Cake/Collector/AssistT00L

- CDN
- CrawlCerts
- CSubnet
- HostCollide
- QueryA
- ScanPort
- SubdomainFriendChins
- VerifyEmails
- WebDetect

### 指纹识别

>Cake/Collector/Finger

- Ehole（二开修改）（https://github.com/EdgeSecurityTeam/EHole）

### Spider（子域名以及敏感路径的爬取）

> 由于ShuiZe的Spider模块的爬取功能,达不到适配该工具所需要的特殊要求,这里采用自己写的爬虫工具(@Bifishone)

- GoogleDomain.py (默认爬取前10页) (禁用)

- EdgeDomain.py (默认爬取前15页)
- EdgeURL.py (默认爬取前15页) 
- Baidu.py (继承了原ShuiZe百度爬取的“鸡肋”功能)

<img width="1156" height="618" alt="image" src="https://github.com/user-attachments/assets/faafcb5c-4359-42ff-905a-c36831748d87" />


### Type

> Cake/Collector/TypeIt  有强迫症，喜欢整整齐齐的~🤨🤨🤨

## 优势对比

domain.txt

~~~txt
camscanner.com
camcard.com
qixin.com
b.qixin.com
textin.com
juzijianzhi.com
b.camcard.com
~~~

> 以下是各工具对于domain.txt中子域名的收集情况（LittleCake）【在相同的网络环境中进行(Windows)】

<u>**在不配置api接口的情况下：**</u>

| 工具名称                   | 扫描用时(≈) | 获得子域名数 | 使用的命令                                                   |
| -------------------------- | ----------- | ------------ | ------------------------------------------------------------ |
| LittleCake                 | 33:55       | 533          | ./LittleCake.exe                                             |
| OneForAll (default)        | 20:02       | 261          | python3 oneforall.py --targets ./domain.txt run              |
| ShuiZe_0x727-1.0 (default) | 20:50       | 146          | python3 ShuiZe.py --domainFile domain.txt --justInfoGather 1 --ksubdomain 0 |

- ShuiZe (https://github.com/0x727/ShuiZe_0x727)
- OneForAll (https://github.com/shmilylty/OneForAll)

<u>**“附魔”之后：**</u>

| 工具名称   | 扫描用时(≈) | 获得子域名数 | 使用的命令       |
| ---------- | ----------- | ------------ | ---------------- |
| LittleCake | **          | 1406         | ./LittleCake.exe |

> 仅收集部分子域名进行对比，最终的收集完整性请自行检测😉😉😉~

## 工具准备

### config.ini及API配置 (请自行申请配置)

## 工具收集概况

### 重要信息收集

<img width="2560" height="1480" alt="image" src="https://github.com/user-attachments/assets/6444497b-9991-4c46-a014-9d8d268a99b2" />


<img width="1846" height="1308" alt="image" src="https://github.com/user-attachments/assets/c1feeb20-24b0-4332-9e7a-85d49411cf71" />


### 微漏扫

> 具体漏洞准确性请自行检查判断~

<img width="319" height="425" alt="image" src="https://github.com/user-attachments/assets/059facdb-a141-4f6d-89f8-2fdb2c6742c4" />


### 邮箱收集

<img width="1137" height="977" alt="image" src="https://github.com/user-attachments/assets/02e595a7-c5b1-4d1b-b245-d3d0aa32d102" />


### 指纹识别

<img width="1906" height="975" alt="image" src="https://github.com/user-attachments/assets/075112e9-dfe0-4e0e-9093-1b89b2c65c20" />


### 等等信息……😉😉

## 作者信息

Bifishone，@https://github.com/Bifishone！
