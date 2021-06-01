---
layout: post
title:  "常用命令"
date:   2016-12-28 20:03:02 +0800
categories: jekyll update
---

覆盖文本内容
echo nameserver 8.8.8.8 > /etc/resolv.conf

在文本内容追加
cat  >> /etc/resolv.conf << EOF
>nameserver 8.8.4.4
>EOF

lsof -i:3000
kill id
强制杀死：kill -9 PID

查看4000端口
netstat -na|grep 4000
检测是否安装ssh
sudo ps -e |grep ssh

Docker 
docker exec  c_name cat /etc/hosts  
进入容器
sudo docker exec -it -privileged  container_id  /bin/bash 
（--dns 8.8.8.8 --dns 8.8.4.4）

docker volume rm $(docker volume ls -qf dangling=true)
1. Delete all containers
docker rm $(docker ps -a -q)
docker volume prune
2. Delete all images
docker rmi $(docker images -q)
3. remove all unused

docker system prune --volume
docker system prune --all





docker 启动nginx服务
docker container run \
-d \
-p 0.0.0.0:8888:80 \
--volume /Users/sky/Desktop/work/frontend-for-pc/dist:/usr/share/nginx/html \
--volume /Users/sky/Desktop/docker/nginx:/etc/nginx \
--volume /Users/sky/Desktop/docker/log:/var/log/nginx:rw \
--rm \
--name mynginx \
nginx


docker run -itd --name youfu_movie \
-v /Users/sky/Desktop/docker/mysql/conf/mysql:/etc/mysql \
-v /Users/sky/Desktop/docker/mysql/data:/var/lib/mysql \
-p 3306:3306 -e MYSQL_ROOT_PASSWORD=root mysql




拷贝文件到容器
docker cp foo.txt 72ca2488b353:/foo.txt
拷贝文件到本机
docker cp 72ca2488b353:/foo.txt foo.txt




express-web 依赖 mongo容器
docker run -itd --name mongo  leonema666/mongo
docker run -it -p 4000:4000 -p 80:4000 --link mongo:mongo -e DOCKER=1 --name web  leonema666/express-web npm run dev

登陆到docker虚拟机
screen ~/Library/Containers/com.docker.docker/Data/vms/0/tty
aws configure
aws s3 cp v1.0.0.zip s3://baoxue.bxbw2.com/html/pc/


默认情况下Docker的存放位置为：/var/lib/docker 
sudo docker info | grep "Docker Root Dir"




Webpack 安装需root 获取管理员权限
 sudo -s

重启网络
sudo ifconfig en0 down
sudo ifconfig en0 up

查找文件
sudo find / -name mongod.lock

nginx常用命令
启动nginx：
sudo nginx		
判断配置文件是否正确
sudo nginx -t		
停止nginx：
sudo nginx -s stop		
重启nginx：
sudo nginx -s reload

检查是否开启gzip
curl -H "Accept-Encoding: gzip" -I http://localhost/test.css

mongodb:
brew services start mongodb
进入mongodb
mongo
show  mongodb
use admin;
db.shutdownServer();

重启centos
shutdown -R now


tree 命令
tree -L 2     显示2个层级的目录

查看系统用的那个shell
echo $SHELL
chsh -s /usr/local/bin/zsh

设置终端前缀 主机名  路径
echo $PS1 
export PS1="%m %~ %d $ "

输出当前用户：whoami
brew install postgresql
psql --version
// 后台启动postgresql
brew services start postgresql
// 前台启动
postgres -D /usr/local/var/postgres
// 停止postgresql
brew services stop postgresql
// 重启postgresql
brew services restart postgresql

首先Object和Function都是构造函数，而所有的构造函数的都是Function的实例对象. 因此Object是Function的实例对象
Function.prototype是Object的实例对象
实例对象的原型(我们以proto来表示)会指向其构造函数的prototype属性, 因此 Object.proto === Function.prototype,Function.proto===Function.prototype,Function.prototype.proto === Object.prototype
当我们访问一个属性值的时候, 它会沿着原型链向上查找, 直到找到或者到Object.prototype.proto(为null)截止.




