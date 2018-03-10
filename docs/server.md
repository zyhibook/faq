# 服务器部署与运维

> [管理平台配置说明](spec/server_config.md)

## 推荐！基于Docker

通过我们发布的Docker镜像，可以快速完成服务器搭建工作，整个过程只需两行命令。

> 如果你没有Docker环境，请看下面的Docker一键安装教程。

````shell
# 请认准我们的官方镜像，无毒无害实时更新
docker pull registry.cn-qingdao.aliyuncs.com/akaxin/openzaly:latest

# hostBaseDir需要更改成你本地的绝对目录，服务器的日志、图片、数据库将存储在这个位置
docker run -tid -v hostBaseDir:/akaxin -p 2021:2021 registry.cn-qingdao.aliyuncs.com/akaxin/openzaly:latest
````

通过上面的两行命令安装完成后

````shell
docker ps -l
````

看到处于运行中的服务，代表程序运行成功，可以通过app访问站点。

## 访问站点

打开应用输入服务器地址，便可访问站点。初次访问的邀请码为`000000`，初次登录的用户默认为站点管理员。

## 一键安装Docker教程

快速安装基于Docker，以下是Docker的一键安装教程，**如果你已经拥有Docker环境，请跳过**。

* Linux
    * 直接通过yum、apt安装即可。
    * 或者访问：https://www.docker.com/community-edition#/download
* [Mac OSX](<https://store.docker.com/editions/community/docker-ce-desktop-mac>)
* [Windows Pro\Server](<https://store.docker.com/editions/community/docker-ce-desktop-windows>)


----

## 通过源码安装阿卡信服务端

### 1. 安装通讯服务器

* gitHub地址：https://github.com/akaxincom/openzaly
	* 执行build.sh生成jar包。

* 运行jar包
	* java -Dsite.port=$PORT -Dhttp.port=$PORT2 -jar openzaly-boot-jar-with-dependencies.jar
	* $PORT 是对用户提供的端口，默认为2021，建议不要修改。
	* $PORT2 是对Server端API提供的端口。

**-jar参数选项：**
```
### site netty tcp address,listen all address
site.address=0.0.0.0

### site netty tcp port
site.port=2021

### http server address
http.address=127.0.0.1

### http port
http.port=8080

### default back-stage management address
site.admin.address=127.0.0.1

### default back-stage management port
site.admin.port=80

### default site Administrators
site.administrators=ZALY_SHAOYE

### first user login site,use this invite code
site.admin.uic=000000

### deposit pictures,audio,db
site.baseDir=./
```

### 2. 管理管理后台

* github地址：https://github.com/akaxincom/site-admin
	* 安装到通讯服务器同一机器上。
	* 参考 nginx配置文件：[源码安装-nginx配置](./源码安装-nginx配置.md


**Zaly_admin_nginx配置文件**

```

# 这只是一个范例而已，并不是copy过去直接用。

# 修改Zaly_admin的存放目录，默认/home
# 修改Zaly_admin log的存放目录，默认/akaxin
# 修改您本机的php-fpm监听端口，默认9000

server {
    listen       80;
    server_name 127.0.0.1;

    charset utf-8;

    access_log /akaxin/plugin_access.log ;
    error_log /akaxin/plugin_error.log ;

    root   /home/zaly_admin;
    index  index.html index.htm index.php;
    location / {
        try_files $uri $uri/ /index.php?$query_string;
    }

    # pass the PHP scripts to FastCGI server listening on 127.0.0.1:9000
    #
    location ~ \.php$ {
        fastcgi_pass   127.0.0.1:9000;
        fastcgi_index  index.php;
        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;

        include        fastcgi_params;
    }
}
```

### 3. 成功搭建站点后，app登陆站点

打开应用输入服务器地址，便可访问站点。初次访问的邀请码为`000000`，初次登录的用户默认为站点管理员。

----

使用过程若有任何问题，欢迎联系我们 feedback@akaxin.xyz
