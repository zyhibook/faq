
在一台服务器（或个人电脑）上启动Akaxin，需要以下步骤。

* [第一步：安装Java运行环境](step-1-java.md)
* [第二步：获取Akaxin服务端程序](step-2-jar.md)
* [第三部：启动服务器](step-3-run.md)

----


# 第一步：安装Java运行环境

> 已有Java环境，或者对此很熟的，请跳过
>
> **Akaxin推荐Java版本：Java 8+**



* 在Windows上安装Java
* 在Mac上安装Java
* 在Linux上安装Java


在Windows上安装Java
====

1. 打开Java 官方下载地址
    * http://www.oracle.com/technetwork/java/javase/downloads/jre10-downloads-4417026.html
2. 下载 jre-10.0.1_windows-x64_bin.exe
    * 需要先选中【 Accept License Agreement】
3. 下载完成后，双击运行即可。


在Mac上安装Java
====

1. 打开Java 官方下载地址
    * http://www.oracle.com/technetwork/java/javase/downloads/jre10-downloads-4417026.html
2. 下载 jre-10.0.1_osx-x64_bin.dmg
    * 需要先选中【 Accept License Agreement】
3. 下载完成后，按提示操作。


在Linux上安装Java
====

Linux用户对用使用yum、apt之类安装软件。

**Centos类用户**

```bash
$ yum search openjdk
$ sudo yum install java-1.8.0-openjdk.x86_64
```

**Ubuntu类用户**

```bash
$ apt search openjdk-9-jre
$ sudo apt install openjdk-9-jre
```
