# app数据抓取

## 导读

- 学会安卓模拟器搭建
- 学会抓包利器使用
- 学会自动化控制工具使用
- 学会利用python编写爬虫app数据
- 打造基于docker的多app端数据抓取系统

### 学会这项技术可以做什么?

- 项目,团队,公司
	- 数据分析
	- 用户画像
	- 统计系统
	- 商业竞争
- 自己
	- 技能提升
		- 掌握抓取app应用数据的技能
		- 面试必问
		- 抓包工具如何使用
		- ...

### app数据好抓么?

1. > 简单
	>
	> app数据比web端更容易抓取,反爬虫也没那么强,大部分也都是HTTP/HTTPS协议,返回的数据类型大多数为json.

2. > 困难
	>
	> 1. 可能需要适当的反编译,分析出加密算法,并抓取到信息。
	> 2. 可能加固,需要脱壳,然后反编译,分析出加密算法并抓取到信息。
	> 3. 需要破解通过各式各样的签名,证书,设备绑定等方法,找到隐藏的加密算法.

### 爬虫工程师技术储备

- python爬虫开发经验
- java开发基础
- android开发基础
- app逆向
- app脱壳
- 破解加密算法

### 课程设计

![image-20210601022136539](https://cdn.jsdelivr.net/gh/yanshaung/pic/image-20210601022136539.png)

> 最终实现
>
> ![image-20210601022239268](https://cdn.jsdelivr.net/gh/yanshaung/pic/image-20210601022239268.png)

## 相关安装与介绍

### 夜神模拟器

[下载地址](https://www.yeshen.com/)

#### 相关配置

pass

------

### 抓包工具

> 抓包工具对比
>
> ![image-20210601130507608](https://cdn.jsdelivr.net/gh/yanshaung/pic/image-20210601130507608.png)

---



#### `fiddler`

[下载地址](https://www.telerik.com/fiddler/fiddler-classic)[^安装在默认路径]



###### 标识符

> ![image-20210601141204791](https://cdn.jsdelivr.net/gh/yanshaung/pic/image-20210601141204791.png)

##### 常用操作

> 
>
> 



---

#### `mitmproxy`

##### 安装方法`pip install mitmproxy`



#### `Packet Capture`

[下载地址](https://www.coolapk.com/apk/app.greyshirts.sslcapture)

---

#### `Apaaium`[^ 移动端自动化测试工具]

[下载地址](https://github.com/appium/appium-desktop/releases/tag/v1.21.0)

---

### docker

[下载地址](https://docs.docker.com/docker-for-windows/install/)

[提示错误](https://www.coder.work/article/7351532)



### ==证书安装==

```text
打开浏览器输入
mitm.it
```



---



## 2. `mitmproxy`手机抓包的使用

### 三个组件

#### 1. `mitmporoxy`[^windows无法使用]

---



#### 2.`mitmdump`

##### 使用方法

###### ==更换监听端口号==

> `pycharm`命令终端
>
> `mitmdump -p 端口号`

###### ==与`python`互交==

> `pycharm`命令终端
>
> `mitmdump -p 端口号 -s ys.py`

---



###### ==抓取手机端请求信息==

==以日志格式打印==

> ```python
> from mitmproxy import ctx
> 
> def request(flow):
>     # print(flow.requests.headers)
>     ctx.log.info(str(flow.requests.headers))   # 请求头信息
>     ctx.log.info(str(flow.requests.url))   # url信息
>     ctx.log.info(str(flow.requests.host))   # 主机头信息
>     ctx.log.info(str(flow.requests.method))   # 请求方法
>     ctx.log.info(str(flow.requests.path))   # 请求路径
>   
> ```
>
> ==在终端进行启动==
>
> `mitmdump -p 端口号 -s ys.py`

---



###### ==抓取手机端响应信息==

 ==以日志格式打印==

> ```python
> from mitmproxy import ctx
> 
> def response(flow):
>  # print(flow.requests.headers)
>  ctx.log.info(str(flow.response.status_code))   # 请求头信息
>  ctx.log.info(str(flow.response.text))   # 返回内容
> 
> ```
>
> 



#### 3.`mitmweb`







----

# 测试

> 连接特定的 DNS 后缀: 
> 描述: Intel(R) Wireless-AC 9462
> 物理地址: ‎14-F6-D8-F3-34-0F
> 已启用 DHCP: 是
> IPv4 地址: 192.168.10.129
> IPv4 子网掩码: 255.255.255.0
> 获得租约的时间: 2021年6月1日 22:10:39
> 租约过期的时间: 2021年6月2日 22:10:39
> IPv4 默认网关: 192.168.10.1
> IPv4 DHCP 服务器: 192.168.10.1
> IPv4 DNS 服务器: 192.168.1.1
> IPv4 WINS 服务器: 
> 已启用 NetBIOS over Tcpip: 是
> 连接-本地 IPv6 地址: fe80::38cd:ee54:26c0:3f88%4
> IPv6 默认网关: 
> IPv6 DNS 服务器: 
