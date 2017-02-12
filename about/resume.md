# PHP简历

---


# 联系方式

- 手机：13726247356
- Email：zhanghaipeng404@gmail.com

---

# 个人信息

 - 张海鹏/男/1992 
 - 本科/软件工程/15年毕业
 - 工作年限：2年
 - GitHub：https://github.com/happen-zhang
 - 期望职位：PHP、后端开发、运维开发
 - 期望薪资：面谈
 - 期望城市：深圳、广州

---

# 工作经历

## 云创股VentureShares（2015年4月 ~ 2017年1月）

### VS主站
公司的主网站，基于 ThinkPHP3.2 框架开发的，部分服务使用 Nginx 与 Lua 的结合实现，比如测试环境切换、部分接口网关等。使用 Migration 管理数据库表模型完整性。数据库 MySQL 主从读写分离，提高系统可靠性和减轻系统压力。系统需求包含大量耗时的日常任务，如大量邮件发送、短信（SMS）发送、爬虫服务，这些采用 Redis 来模拟消息队列来实现。计时器任务则采用 Redis 键事件 expired 来模拟计时器。同时使用 Supervisor 来保证这些后台守护进程能够稳定运行。结合 Linux 的 crontab 来完成每日的定时数据备份。系统需要提供微信公众号功能、微信网页授权，所以 系统账号需要和 unionid 相结合，以完成对某一用户的标记。编写 shell 脚本完成部分自动化任务，如 Linux 用户添加、安装系统软件依赖、修改防火墙设置、服务监控重启等。

### VS合伙人
这是公司的另外一个平台，采用前后端分离的方式开发的。后台所有基础服务都是基于 Docker 来部署运行的，包括 PHP7.1、Nginx 代理、Swoole 服务、MySQL 数据库、队列服务、Zabbix 监控等十多个服务。框架从 Slim3 转为 Laravel5.2，系统提供 Restful 接口、JWT 权限认证、请求过滤等，使用 Laravel 的 Schema 代替 crontab 来管理定时任务，期间也熟悉了 Laravel 的源码。由于微信网页授权有域名个数限制，因此需要对域名解析然后组装 URL 分发到目标站。之前系统架构为 Nginx 结合 php-fpm，后来把 Laravel 与 Swoole 结合，使后端整体性能提升了 20 多倍。运维方面做了一键自动化部署、回滚代码功能，Docker 服务监控重启脚本等。项目期间完善了几个小工具集，如集成线上环境的 Dockerfile 集合、API 执行期间的[数据收集器](https://github.com/happen-zhang/data-collector)等。

### 独角兽公司（小程序）
这个微信小程序主要以呈现为主，数据来源为国外多个知名网站，爬取数据同时使用第三方接口分析相关指数、正负面指数等。后端需要处理微信小程序用户的信息获取，由于微信各平台接口的不统一，小程序的用户信息获取需要使用单独的接口来完成。
 
## 广东好旅行 （2014年10月 ~ 2015年2月）

### OK珠海 
这是一个面向珠海本地用户的 O2O 产品，现已推出了用户版（ App 版）和商家版（ Web 版）。我在这个项目中负责的部分是整个后端的功能设计、数据库设计、接口开发和服务器搭建运维。整个项目的后端搭建是基于 PHP，MySQL 和 Nginx 的，数据缓存使用的是 Redis，接口一部分使用 Restful 风格进行设计。项目涉及了LBS、第三方推送服务和 WebSocket 等需求的开发。编写监控服务器的 shell 脚本，保证服务器能够可靠运行。

## 魅族（2014年4月 ~ 2014年9月）

### 笔戈科技 
这个是「魅族科技」旗下的一个有知名度的科技媒体网站，项目其实之初获得外界的大量关注。它是基于 Node.js 的 Ghost 博客系统进行二次开发完成的。这个项目在 Ghost 的基础上进行的扩充，添加了基于 RBAC 的多用户权限管理。目前网站的日均 PV 在 100000 左右。

## 北纬21°工作室（2012年1月 ~ 2014年3月）

### 外包项目

合伙于「北纬21°工作室」，负责网络部的开发工作，开发校园内部和校外商家的定制网站。主要任务有网站搭建、服务器搭建和域名购买部署。能够快速建设网站，至今独立完成的外包项目多于 10 个。

---

# 开源项目和作品

## 开源项目

### easy-admin系统

这是一个通用后台管理系统，它能够帮你创建一个方便可用的后台信息管理，并集成一些常用的操作。例如，帮你轻松搞定信息的 CURD 、权限管理（多管理员）、数据文件管理和数据库备份恢复功能等等。不仅功能众多，界面友好，同时也方便开发者进行二次开发。这款应用在 ThinkPHP 社区中已获得了一定数量的用户。[项目地址](https://github.com/happen-zhang/easy-admin)。

### symfony教程

这是一系列 Symfony 相关的翻译教程。鉴于国内关于 Symfony2 的资料稀缺，而且 Symfony 在国外又有相当的知名度，于是就做了这一系列工作。全文一共 19 章，并开源到 GitHub 上供有需要的同学学习使用。目前该教程正在和国内的 Symfony 社区尝试共同维护发布。[项目地址](https://github.com/happen-zhang/symfony2-jobeet-tutorial)。

### mungbean

基于 Node.js 的简单、易容、强大的 ORM 工具。Mungbean 的设计思路有点不同，它的设计思路和传统 ORM 的设计思路还是有比较大的区别的，从而可实现更多灵活的数据库操作。Mungben 文档目前比较齐全，简单易用，合适拿来做中小型的 Node.js 项目。[项目地址](https://github.com/happen-zhang/mungbean)。

### cakes

这是一个为 Javascript 编写的简单 class-like 接口，通过这个库可以对 Javascript 编写类似于 PHP 或 Java 那样的类继承代码。这个库已发布到 npm 上。[项目地址](https://github.com/happen-zhang/cakes)。

### ThinkPHP

贡献过ThinkPHP的源码。[贡献地址](https://github.com/happen-zhang/thinkphp/graphs/contributors)。

## 参考链接

- CSDN：http://blog.csdn.net/happen_zhang
- V2EX：https://www.v2ex.com/member/a15819620038
- 知乎：https://www.zhihu.com/people/zhang-hai-peng-14/activities

# 技能清单

以下均为我熟练使用的技能

- Web后端开发：PHP/Node/C/Java
- Web后端框架：Laravel5/ThinkPHP/Slim/Swoole/Workerman
- 系统运维：shell
- 数据库相关：MySQL
- 版本管理和包管理工具：Git/Composer
- 单元测试：PHPUnit
- 云和开放平台：微信应用开发等
- 网络编程：socket编程/Swoole/Workerman
- 基础：熟悉Linux、HTTP协议、TCP/IP协议族/操作系统原理/基础算法

---

# 致谢
感谢您花时间阅读我的简历，期待能有机会和您共事。
