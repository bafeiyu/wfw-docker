# 开发环境搭建



### 基础环境：

#### Linux：centos7.6

#### Docker version 19.03.12

#### docker-compose version 1.26.2



### docker容器：

​```
php 7.4.11 
	ext: swoole4.5 redis5.0 
mysql5.7
	系统默认账户/密码: root/root
	测试数据库/账户/密码: test/test/test	
​```


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



