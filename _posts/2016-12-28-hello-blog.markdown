---
layout: post
title:  "hell blog jekyll"
date:   2016-12-28 20:03:02 +0800
categories: jekyll update
---
Appid:
m0105478428@gmail.com
Mlxy0909

KOCMF7H6RZWGBGML

Git:
m0105478428@gmail.com
laotie666

redmine 
leonema
leone123456

Alin09
skytalking

测试账号：
test666
asdasd

Centos
rootleonema

测试公司后台:  admin.zjgguolong.com
superadmin  /  qweqwe123
wap.zjgguolong.com  前台
app.zjgguolong.com   接口
422057  中国龙的邀请码

http://admin.94flash.com/
http://admin.sg04.com/
qweqwe
qweqwe
asdasd
asdasd

查看4000端口
netstat -na|grep 4000
检测是否安装ssh
sudo ps -e |grep ssh

Docker 
docker exec  c_name cat /etc/hosts  
进入容器
sudo docker exec -it -privileged  container_id  /bin/bash   


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

mongodb:
brew services start mongodb
进入mongodb
mongo
show  mongodb
use admin;
db.shutdownServer();

Unifiskytalking1234


if (obj.ac === 'getSportMetaList') {
          res.data = {
            msg: 50003,
            param: 'System is maintaining',
            data: {
              maintenance_time: '13:00:00 - 18:00:00'
            }
          }
        }

DynamicForm
<form :action="data.url" :method="data.method" target="iframe">
    <input type="text" v-for="(val,key) in data.data" :key="key" :name="key" :value="val" v-show="false">
    <iframe name="iframe" style="width: 100%; border: 0;"></iframe>
  </form>
if (this.$route.name == "maintained") return this.$router.go(-2);


