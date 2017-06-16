# 高可用的MongoDB集群

**安装**

```
# 进入到/usr/local/目录
cd /usr/local/
# 在当前目录下创建tools目录并进入
mkdir -p tools & cd tools
# 下载
wget -c https://fastdl.mongodb.org/linux/mongodb-linux-x86_64-rhel70-3.4.5.tgz
# 解压
tar -xzvf mongodb-linux-x86_64-rhel70-3.4.5.tgz
# 重命名
mv mongodb-linux-x86_64-rhel70-3.4.5 mongodb3.4.5
# 创建目录
cd ../ & mkdir -p mongodb
# 把刚才解压的文件夹整个移过来
mv tools/mongodb3.4.5/ mongodb/
# 进入
cd mongodb/mongodb3.4.5

```



