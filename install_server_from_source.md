# 通过源码安装阿卡信服务端

## 安装通讯服务器

* gitHub地址：https://github.com/akaxincom/openzaly
	* 执行build.sh生成jar包。

* 运行jar包[源码安装-jar参数选项](./源码安装-jar参数选项.md)
	* java -Dsite.port=$PORT -Dhttp.port=$PORT2 -jar openzaly-boot-jar-with-dependencies.jar
	* $PORT 是对用户提供的端口，默认为2021，建议不要修改。
	* $PORT2 是对Server端API提供的端口。

## 管理管理后台
	
* github地址：https://github.com/akaxincom/site-admin
	* 安装到通讯服务器同一机器上。
	* 参考 nginx配置文件：[源码安装-nginx配置](./源码安装-nginx配置.md)

