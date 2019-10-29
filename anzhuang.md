# 安装

下载地址:https:\/\/www.mongodb.com\/download-center?jmp=homepage\#community

选择对应版本:

```
curl -O https://fastdl.mongodb.org/linux/mongodb-linux-x86_64-rhel70-3.4.0.tgz
tar -zxvf mongodb-linux-x86_64-rhel70-3.4.0.tgz
mv mongodb-linux-x86_64-rhel70-3.4.0/ /usr/local/mongodb
# 添加PATH到常量中
export PATH=/usr/local/mongodb/bin:$PATH
```

MongoDB默认的启动的数据库路径\(--dbpath\)是\/data\/db.可以通过--dbpath指定数据库目录,但默认的也要手动创建:

```
mkdir -p /data/db
```

MongoDB Shell是后台自带交互式JavaScript shell,用来对MongoDB进行操作和管理的交互式环境.使用mongo\(添加环境变量后\)进入后台后,默认会链接到test文档\(数据库\).

由于是JavaScript shell,可以运行一些简单的算术运算.

**Web用户界面**

```
./mongod --dbpath=/data/db --rest
```

MongoDB的Web界面访问端口比服务的端口多1000.http:\/\/localhost:28017

# 启动

**启动常用参数**

* dbpath - 数据文件存储路径:\/data\/mongodb

* logpath - 日志路径 : \/var\/log\/mongodb\/mongodb.log

* logappend - 日志使用追加代替覆盖 : true

* bind\_ip - 绑定的IP:10.10.10.10

* port - 绑定的端口:27107

* journal - 写操作首先写入日志:true


**启动方式**

**1.简单前台启动** - 仅仅指定数据目录,使用默认的27107端口.

```
./mongod --dbpath=/path/mongodb
# 直接本机使用mongo链接
./mongo
```

**2.启动绑定固定的IP地址,端口** - mongo在连接mongod的时候就需要指定IP和端口了

```
./mongod --dbpath=/path/mongodb --bind_ip=10.10.10.10 --port=12345
# 链接mongo
./mongo 10.10.10.10:12345
```

**3.daemon后台运行**

```
# 简单的是在命令后面加 &
./mongod --dbpath=/path/mongodb --bind_ip=10.10.10.10 --port=12345 &
# 使用mongo自带参数,但是需要必须指定log的路径
./mongod --dbpath=/path/mongodb --fork=true logpath=/path/mongod.log
```

**4.以配置文件形式启动\(推荐\)**

```
aport=12345
bind_ip=10.10.10.10
logpath=/path/mongod.log
pidfilepath=/path/mongod.pid
logappend=true
fork=true
# 启动时使用
./mongod -f /path/mongod.conf
```

# 关闭

1.前台运行

直接退出终端关闭即可,Mongodb将会自己做清理退出,把没有写好的数据写完成,并最终关闭数据文件.要注意的是这个过程会持续到所有操作都完成.

2.后台运行

如果是使用--fork在后台启动Mongo,就要向服务器发送关闭消息关闭了.

```
use admin
db.shutdownServer()
# 这里的命令只允许在本地,或是一个经过认证的客户端
```

3.主从式的复制集群\(1.9.1版之后\)

检查从Mongodb的数据更新时间

如果所有的从Mongodb和主的时间差都超过10，这个时候不会关闭mongodb（在这种情况下面，我们可以通过配置timeoutSecs的方式来让从Mongodb完成数据的更新）

如果其中有一个从Mongodb与主服务时间差在10秒内，那么主服务器将会关闭，并且等待从Mongodb更新完成并关闭。



如果没有up-to-date 从Mongodb且你想强制关闭服务，可以通过添加force:true;命令如下：

&gt; db.adminCommand\({shutdown : 1, force : true}\)

&gt; \/\/or

&gt; db.shutdownServer\({force : true}\)

指定特定超时时间的关闭服务器，命令同上，另外加上一个timeoutsec:参数

&gt; db.adminCommand\(shutdown : 1, force : true, timeoutsec : 5\)

&gt; \/\/or

&gt; db.shutdownServer\({force : true, timeoutsec : 5}\)

