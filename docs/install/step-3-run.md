
在一台服务器（或个人电脑）上启动Akaxin，需要以下步骤。

* [第一步：安装Java运行环境](step-1-java.md)
* [第二步：获取Akaxin服务端程序](step-2-jar.md)
* [第三部：启动服务器](step-3-run.md)

----


# 启动服务器

都准备完成了，这一步便是启动服务器了。

在启动服务器之前，需要说明两个概念：`当前工作目录` 与 `site.baseDir`

服务器是需要一个目录来保存数据库、图片等文件的，这些东西保存在 `site.baseDir` 目录下，如果你没有特殊指定的话，默认是进程的 `当前工作目录`

> **当前工作目录**
>
> 又叫做 `当前运行目录`
>
> 在哪一个文件夹下执行 `java -jar` 程序，哪一个文件夹，就是Akaxin服务端程序的 `当前工作目录`


服务器的启动命令
====

**默认参数启动**

```
$ java -jar openzaly-server.jar
```


**修改参数**

支持以下启动参数，可以通过 `java -jar openzaly-server.jar -h` 参数查阅。

常用的参数有：

```
-Dsite.address 		openzaly Netty address default:0.0.0.0，设置服务器监听的IP，默认监听所有。
-Dsite.port 		openzaly Netty port default:2021，主服务器的监听端口，默认2021。
-Dhttp.address 		openzaly Http address default:0.0.0.0，innerAPI监听的IP，默认所有。
-Dhttp.port 		openzaly Http port default:8280，innerAPI监听的端口，默认8280
-Dsite.admin.address 	openzaly AdminSystem address default:127.0.0.1，管理平台监听的IP，默认本机。
-Dsite.admin.port 	openzaly AdminSystem port default:8288，管理平台监听的端口，默认8288
-Dsite.admin.uic 	openzaly first uic for admin port default:000000，首次启动管理员使用的邀请码，默认000000
-Dsite.baseDir 		openzaly openzaly-server root dir default:./，系统默认存储目录。
```

**比如想修改主服务器启动的端口为12345**

```
$ java -jar  -Dsite.port=12345 openzaly-server.jar
```


在服务器上启动程序
====

* 在Windows上启动服务器
* 在Mac、Linux上启动服务器


在Windows上启动服务器
----

1. 打开cmd命令行工具
2. 通过 cd 命令切换到 jar包 所在的目录
3. 输入 dir 命令，确认输出中，有jar文件。
4. 输入服务器启动命令


在Mac、Linux上启动服务器
----

1. 打开终端
2. 通过 cd 命令切换到jar包所在目录
3. 输入服务器启动领命
