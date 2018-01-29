### docker 搭建服务器

1. 拉取镜像

		docker pull registry.cn-qingdao.aliyuncs.com/akaxin/openzaly:latest

2. 运行镜像
	
		docker run -tid -v hostBaseDir:/akaxin -p hostPort:2021 registry.cn-qingdao.aliyuncs.com/akaxin/openzaly:latest
		
	例如：
	
		docker run -tid -v /akaxin:/akaxin -p 2021:2021 registry.cn-qingdao.aliyuncs.com/akaxin/openzaly:latest

	* hostBaseDir 您本机数据存储的位置，如log, db 等
	* hostPort 您本机共网可以访问的ip:port

3. 查看镜像
	
		docker ps -l
	
	* 看到镜像，处于运行中，代表镜像运行成功，可以通过app访问站点
