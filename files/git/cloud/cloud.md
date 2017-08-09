## 云相关概念

![](../image/cloud/云计算的组成.png)

### LAAS 

基础设施即服务

1. 计算与网络
	- 云服务器CVM
	- 私有网络VPC
	- 负载均衡CLB
	- 云数据库CDB
2. 存储与内容分发
	- 对象存储COS
	- 内容分发网络CDN
3. 数据库
	- 云数据库CDB
	- 云存储Redis
	- 云缓存Memcached

### PAAS

平台即服务
1. 音视频方案、消息推送

### SAAS

软件即服务
1. 云盘、在线文档协作

### CDN(Content Delivery Network)

内容分发网路,通过分布在全球各地的机房为用户提供就近接入

**CDN调度原理:**

DNS,域名系统。通过主机名，最终得到该主机名对应的IP地址

![](../image/cloud/CDN原理.png)


### GSLB(Global Server Load Balancing)技术
全球服务器负载均衡，用于灾备和路由优化



### COS(Cloud Object Storage)

面向厂商和开发者的网络硬盘，替代传统服务器硬盘和数据存放方式的存储解决方案

### BGP(Border Gateway Protocol) 边界网关协议

用来连接 Internet 上的独立系统的路由选择协议

**应用：**

1. 为运营商之间的互联提供了稳定而安全的路由协议 
2. 自主网络系统中网关之间交换器路由信息的协议，互联网的网关之间