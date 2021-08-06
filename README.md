# bt-lnmp：宝塔一键部署LNMP环境

### @镜像说明
&ensp; 该镜像为宝塔Linux面板Docker化，内部已搭建好LNMP环境，所有软件采用编译形式安装，方便自定义安装组件。<br/>

&ensp; 拉取bt-lnmp镜像、运行容器，即可实现一键部署LNMP开发环境，使用宝塔面板管理服务，方便快捷。

&ensp; 最后更新时间：2021-08-06

### @系统软件安装说明

* CentOS 7.9
* 宝塔面板免费版 7.6.0
* Nginx 1.21.0
* PHP 7.4
* MySQL 5.7.34
* Redis 6.2.4
* MongoDB 4.4.6

### @镜像使用说明

***1、拉取镜像***

```
docker pull msllws/bt-lnmp:1.0
```

***2、运行容器***

```
#与宿主机共用网络，不用做端口映射
docker run -itd --name bt-lnmp --net=host --privileged=true -v /home/www:/www/wwwroot msllws/bt-lnmp:1.0 /usr/sbin/init

#Win或Mac环境下不支持--net=host，需要做端口映射
docker run -itd --name bt-lnmp -p 20:20 -p 21:21 -p 80:80  -p 443:443 -p 3306:3306 -p 8888:8888 --privileged=true -v /home/www:/www/wwwroot msllws/bt-lnmp:1.0 /usr/sbin/init
```

&ensp; /home/www 为自定义宿主机映射目录，用于持久化存放项目文件，以防删除容器后项目文件丢失。

***3、登录宝塔***

```
访问地址：http://主机IP:8888/30d4466b
用户名：bt-lnmp
密码：bt-lnmp666
```

### @其他

* 使用时请遵守宝塔相关协议<br/>

&ensp; 《开源许可协议》：https://www.bt.cn/kyxy.html <br/>

&ensp; 《用户协议》：https://www.bt.cn/fwxy.html <br/>

* DockerHub地址：https://hub.docker.com/r/msllws/bt-lnmp <br/>

* GitHub地址：https://github.com/msllws/bt-lnmp <br/>


### @给个Star，支持一下！
