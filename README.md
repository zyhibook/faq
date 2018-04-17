> 在线访问：https://www.akaxin.com/docs/


Akaxin
====

[![License](https://img.shields.io/badge/license-apache2-blue.svg)](LICENSE)

阿卡信是一款开源免费的即时通讯解决方案，可以帮助你快速建立起自己的移动社交站点，用于即时通讯、业务定制等。

快速体验
----

**基于Docker自动部署服务器**


```
# 请认准我们的官方镜像，无毒无害实时更新
docker pull registry.cn-qingdao.aliyuncs.com/akaxin/openzaly:latest

# hostBaseDir需要更改成你本地的绝对目录，服务器的日志、图片、数据库将存储在这个位置
docker run -tid -v hostBaseDir:/akaxin -p 2021:2021 registry.cn-qingdao.aliyuncs.com/akaxin/openzaly:latest
```

**下载客户端**

> * [iOS](https://itunes.apple.com/cn/app/%E9%98%BF%E5%8D%A1%E4%BF%A1/id1346971087?mt=8)
> * [Android](https://www.akaxin.com)

**访问站点**

> * 生成身份
> * 输入站点服务器
> * 首次登陆为管理员，邀请码：000000
> * 别的用户登陆后可以互加好友，开始聊天。
