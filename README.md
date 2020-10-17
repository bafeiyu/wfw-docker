# 开发环境搭建



### 基础环境：

#### Linux：centos7.6

#### Docker version 19.03.12

#### docker-compose version 1.26.2


### 安装环境
1. 安装虚拟机，破解
2. 导入虚拟机镜像
3. 创建共享文件目录
4. 修改虚拟网络配置 
	`vi /etc/sysconfig/network-scripts/ifcfg-ens32`
	`IPADDR ip段.100`
	`GATEWAY ip段.2`
5. 重启网卡
	`service network restart`
6. 下载docker编排文件
	`cd /www`
	`git clone https://github.com/dinofei/wfw-docker.git docker`		
7. 修改docker-compose.yml的挂在目录为本地创建的目录名称
8. 安装容器
	`docker-compose up -d`	
	如果出现IPv4 forwarding is disabled. Networking will not work：
	`vi /etc/sysctl.conf`
	`net.ipv4.ip_forward=1`
	`service network restart`
9. 进入容器下载框架，启动
	`docker exec -it php74 sh`
	`composer create-project hyperf/hyperf-skeleton`
	`php hyperf-skeleton/bin/hyperf.php start`
10. 在宿主机启动框架
	`docker exec -it php74 sh -c "php hyperf-skeleton/bin/hyperf.php start"`		


### docker容器：

```
php 7.4.11 
	ext: swoole4.5 redis5.0 
mysql5.7
	系统默认账户/密码: root/root
	测试数据库/账户/密码: test/test/test
```


### 容器基本使用

#### 启动所有容器

`docker-compose up -d`

#### 移除所有容器

`docker-compose down`

#### 进入容器

`docker exec -it container_name sh`
`docker exec -it container_name bash`

#### 在宿主机执行容器命令

`docker exec -it container_name sh -c "your_shell_command"`



