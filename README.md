# 基于Spring Security + OAuth2 的SSO单点登录（服务端）

>客户端地址：https://github.com/Janche/sso-oauth2-client
### 完成功能
-[x] 单点登录
-[x] 单点退出

### 系统架构
1. Spring Security
2. OAuth2
3. Redis

### 整体流程
用户访问客户端，客户端 security 发现此请求的用户未登录，于是将请求重定向到服务端认证，
服务端检测到此请求的用户未登录，则将此请求跳转到服务端提供的登录页面(前后端分离则是前端登录地址，否则为服务端内置的登录页面)，
登录成功后，服务端将系统的权限信息（为了减轻服务端的访问压力）和用户的特有标志（如用户名，记录此用户的登录状态）存入redis，
然后服务端会跳回到用户第一次访问客户端的页面。

### 详情请看这里
单点登录客户端：https://blog.csdn.net/qq_34997906/article/details/100014815
单点登录服务端：https://blog.csdn.net/qq_34997906/article/details/97007709

