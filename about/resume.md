# 张海鹏 - PHP简历

---


# 联系方式

- 手机：13726247356
- Email：zhanghaipeng404@gmail.com

---


# 个人信息

 - 张海鹏/男/1992 
 - 本科/软件工程/2015年毕业
 - 工作年限：2年
 - GitHub：https://github.com/happen-zhang
 - 期望职位：PHP、后端开发、运维开发
 - 期望薪资：面谈
 - 期望城市：深圳、广州

---


# 工作经历


## 云创股（2015年4月 ~ 2017年1月）


### 云创股主站

网站地址：[https://www.venture-shares.com](https://www.venture-shares.com/)

主要职责：服务器运维、PHP代码开发、编写部分前端页面、开发资产管理

关键字：CentOS6.8，ThinkPHP3.2，OpenResty，Migration，Redis，MySQL，Shell，任务队列，服务器安全，服务灾备

* 基于 ThinkPHP3.2 框架开发
* 部分服务使用 Nginx 与 Lua 的结合，实现测试环境切换、部分接口网关等
* 使用 Migration 管理数据库表模型完整性
* 数据库 MySQL 主从备份，并实现读写分离，提高系统可靠性和减轻系统压力
* Redis任务队列，处理大量邮件（Email）发送、短信（SMS）发送、数据爬虫
* Redis模拟计时器，实现XX分钟后处理XX任务
* Supervisor管理PHP后台守护进程
* Crontab结合Git完成每日的数据库物理备份，备份文件加密上传
* RESTful风格接口实现
* 微信网页授权、微信公众号开发，关联系统用户
* Shell自动化脚本，增删ssh用户、数据备份、服务存活等
* 服务器初始化搭建、账号安全管理、防火墙（iptables）配置

### 云创股合伙人

网站地址：[https://partner.venture-shares.com](https://partner.venture-shares.com/)

主要职责：服务器运维、全PHP代码开发、交付接口、开发资产管理

关键字：CentOS7，Docker，Laravel5.2，Slim3，Swoole，Nginx-Proxy，JWT、前后端分离，自动化部署、读写分离

* 基于PHP7.1，框架从Slim3转为Laravel5.2
* Nginx-Proxy转发后端多个服务，添加多一层负载均衡器，以备后期扩展多主机扩展
* Swoole结合Laravel，改变原有的PHP运行机制，性能提升10多倍
* RESTful风格接口，JWT无状态权限认证
* 挖掘Laravel源码，充分使用Laravel生态圈轮子，提高开发效率
* 自动化部署工具，实现代码部署、回滚功能
* 微信域名转发，支持一个绑定域名多个子域名转发
* 所有服务基于Docker容器来部署、运行、管理的，编排工具使用docker-compose V2
* 服务镜像全为自定制的Dockerfile来制作
* 实现API接口执行期间性能数据的收集器：[data-collector](https://github.com/happen-zhang/data-collector)

### 独角兽公司

小程序名称：独角兽公司

主要职责：PHP代码开发、交付接口

关键字：微信小程序用户数据接口、数据爬虫

* 小程序获取用户信息的接口
* 多进程数据爬虫实现
 
## 广东好旅行 （2014年10月 ~ 2015年2月）


### OK珠海 

网站地址：[http://m.okhaolvxing.com/](http://m.okhaolvxing.com/)

主要职责：Android开发、服务器运维、PHP代码开发

关键字：Android、WebSocket、百度LBS、第三方推送服务、商家平台搭建

* PHP后台开发和App开发，一把手
* 接入LBS，实现签到功能
* 商家入驻平台，类似于淘宝，服务对象为旅游局
* WebSocket结合Redis实现多人在线小游戏
* 接入各种第三方平台接口
* 服务器运维

## 魅族（2014年4月 ~ 2014年9月）

### 笔戈科技

网站地址：[http://bigertech.com](http://bigertech.com/)

主要职责：完成需求开发

关键字：Nodejs，Ghost二次开发，RBAC，Promise

* 基于著名的Ghost博客系统二次开发的
* 实现多账号（当时版本只支持单一账号）的RBAC权限管理
* Promise解除深层回调

## 北纬21°工作室（2012年1月 ~ 2014年3月）

### 外包项目

主要职责：独立完成外包项目

关键字：PHP、Java、外包

* 独立完成PHP、Java外包项目
* 开发校园内部和校外商家的定制网站

---

# 开源项目和作品

## 开源项目

### Easy-Admin系统

项目地址：[https://github.com/happen-zhang/easy-admin](https://github.com/happen-zhang/easy-admin)

**Star次数：220+**

这是一个通用后台管理系统，它能够帮你创建一个方便可用的后台信息管理，并集成一些常用的操作。例如，帮你轻松搞定信息的 CURD 、权限管理（多管理员）、数据文件管理和数据库备份恢复功能等等。不仅功能众多，界面友好，同时也方便开发者进行二次开发。这款应用在 ThinkPHP 社区中已获得了一定数量的用户。

### Symfony教程

项目地址：[https://github.com/happen-zhang/symfony2-jobeet-tutorial](https://github.com/happen-zhang/symfony2-jobeet-tutorial)

**Star次数：110+**

这是一系列 Symfony 相关的翻译教程。鉴于国内关于 Symfony2 的资料稀缺，而且 Symfony 在国外又有相当的知名度，于是就做了这一系列工作。全文一共 19 章，并开源到 GitHub 上供有需要的同学学习使用。目前该教程正在和国内的 Symfony 社区尝试共同维护发布。

### ThinkPHP

贡献地址：[https://github.com/happen-zhang/thinkphp/graphs/contributors](https://github.com/happen-zhang/thinkphp/graphs/contributors)

贡献过 ThinkPHP 的源码，所属为Model部分代码。

### Mungbean

项目地址：[https://github.com/happen-zhang/mungbean](https://github.com/happen-zhang/mungbean)

基于 Nodejs 的简单、易容、强大的 ORM 工具。Mungbean 的设计思路有点不同，它的设计思路和传统 ORM 的设计思路还是有比较大的区别的，从而可实现更多灵活的数据库操作。Mungben 文档目前比较齐全，简单易用，合适拿来做中小型的 Nodejs 项目。

### Cakes

项目地址：[https://github.com/happen-zhang/cakes](https://github.com/happen-zhang/cakes)

这是一个为 Javascript 编写的简单 class-like 接口，通过这个库可以对 Javascript 编写类似于 PHP 或 Java 那样的类继承代码。这个库已发布到 npm 上。

---

# 技能清单

- Web后端开发：PHP/C/Nodejs/Java
- Web后端框架：Laravel5/ThinkPHP/Slim/Swoole/Workerman
- Web前端：JavaScript/CSS/JQuery
- 系统运维：Shell/Docker
- 数据库相关：MySQL/Redis
- 版本管理和包管理工具：Git/Composer
- 单元测试：PHPUnit
- 云和开放平台：微信应用开发等
- 网络编程：Socket编程/Swoole/Workerman
- 基础：熟悉Linux、HTTP协议、TCP/IP协议族/操作系统原理/基础算法/数据结构

# 自我描述

- 拥抱服务器后端开发的新技术，思考对比技术之间的本质差异
- 不忘牢固基础，刨根问底
- 乐于分享交流，共同进步

## 参考链接

- CSDN：http://blog.csdn.net/happen_zhang
- 知乎：https://www.zhihu.com/people/zhang-hai-peng-14/activities

---
