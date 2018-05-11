<p align="right">
  <a href="https://www.akaxin.com/">
    <img
      alt="Akaxin"
      src="https://avatars3.githubusercontent.com/u/32624098?s=200&v=4"
      width="128"
    />
  </a>
</p>

Akaxin
====

[![License](https://img.shields.io/badge/license-apache2-blue.svg)](LICENSE)

Akaxin 是一款开源免费的聊天软件、代码，可以帮助大家快速在自己的服务器上搭建一套聊天服务，以满足特定场景（如公司办公沟通）的网络安全需求、法律合规需要等。

反馈与建议，请联系 hi@akaxin.xyz

特性：

* 单聊、群聊（含文字、图片、语音等）
* 端到端的加密消息（服务端不可解密，服务器可通过配置关闭此特性）
* 匿名注册、实名注册，以及注册邀请码机制（只允许特定用户注册）
* 扩展机制
* 等

> 在线访问：<b>https://www.akaxin.com/docs/</b>



快速体验
=====

我们提供了两种方式搭建自己的服务器，<b>基于基于jar包或者Docker部署服务器。</b>

* [基于jar包部署服务器](#jarPackage)
* [访问站点服务器](#loginSite)
* [下载客户端](#appDownload)
* [基于Docker部署服务器](#docker)


### <h3 id="jarPackage">**基于jar包部署服务器**</h3>

* 项目地址: https://github.com/akaxincom/openzaly
* 最新版本: 
	* [Github下载](<https://github.com/akaxincom/openzaly/releases>)

	* Gitee下载: 下载链接

* 启动命令：

```
java -jar openzaly-server.jar
```
* 支持的启动参数：

```
java -jar openzaly-server.jar -h
```
```
  -Dsite.project.env  openzaly server environment default:ONLINE
  -Dsite.version    openzaly server version default:0.3.2
  -Dsite.address    openzaly Netty address default:0.0.0.0
  -Dsite.port     openzaly Netty port default:2021
  -Dhttp.address    openzaly Http address default:0.0.0.0
  -Dhttp.port     openzaly Http port default:8080
  -Dsite.admin.address  openzaly AdminSystem address default:127.0.0.1
  -Dsite.admin.port   openzaly AdminSystem port default:8081
  -Dsite.admin.uic  openzaly first uic for admin port default:000000
  -Dsite.baseDir    openzaly openzaly-server root dir default:./
  -Dgroup.members.count   openzaly Max group member size default:100
```

### <h3 id="appDownload">**下载客户端**</h3>


> * [iOS](https://itunes.apple.com/cn/app/%E9%98%BF%E5%8D%A1%E4%BF%A1/id1346971087?mt=8)
> * [Android](https://www.akaxin.com)

### <h3 id="loginSite">**访问站点**</h3>


> * 生成自己的账户
> * 输入站点服务器地址
> * 首次登陆为管理员，邀请码：000000。 <b>管理员登录之后，请在管理后台管理站点的基本信息</b>
> * 将站点服务器地址分享给好友，app中添加为好友之后，就可以开始聊天了。


<p align="center">
  <img align="center" src="https://is1-ssl.mzstatic.com/image/thumb/Purple118/v4/5f/56/82/5f56825f-5a1d-751a-76ee-e4af3337133c/pr_source.png/0x0ss.jpg" width="200"  /> &nbsp; <img align="center" src="https://is1-ssl.mzstatic.com/image/thumb/Purple128/v4/0a/13/7f/0a137f45-a89e-57d6-3135-5c72b219b28d/pr_source.png/0x0ss.jpg" width="200"  /> &nbsp; <img align="center" src="https://is1-ssl.mzstatic.com/image/thumb/Purple128/v4/45/ec/0a/45ec0a96-6683-049e-139b-f11aaea306c8/pr_source.png/0x0ss.jpg" width="200"  /> &nbsp;
</p>

### <h3 id="docker">**基于Docker自动部署服务器**</h3>

请认准我们的官方镜像，无毒无害实时更新

```
docker pull registry.cn-qingdao.aliyuncs.com/akaxin/openzaly:latest
```

> baseAkaxin需要更改成你本地的目录，服务器的日志、图片、数据库将存储在这个位置。
> 
> 2021为默认的端口号，如果有需要改，请修改第一个2021，第二个2021修改后，可能导致服务器地址无法正常访问
> 
> <b>官方建议更改baseAkaxin的目录位置，如果没有修改，可能导致docker重启之后，会出现数据丢失的现象</b>

```
docker run -tid -v baseAkaxin:/akaxin -p 2021:2021 registry.cn-qingdao.aliyuncs.com/akaxin/openzaly:latest
```