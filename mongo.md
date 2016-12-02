# MongoDB简介

MongoDB是由C++语言编写,分布式文件存储,开源数据库系统.

MongoDB将数据存储为一个文档,数据结构由键值对组成,类似JSON对象.

字段值可以包含其他文档,数组及文档数组.

**主要特点**

* MongoDB的提供了一个面向文档存储,操作起来比较简单和容易.
* 可以在MongoDB记录中设置任何属性的索引\(如:FirstName="Sameer",Address="8 Gandhi Road"\)来实现更快的排序.
* 可以通过本地或者网络创建数据镜像,这使得MongoDB有更强的扩展性.
* 如果负载的增加\(需要更多的存储空间和更强的处理能力\),它可以分布在计算机网络中的其他节点上这就是所谓的分片.
* Mongo支持丰富的查询表达式.查询指令使用JSON形式的标记,可轻易查询文档中内嵌的对象及数组.
* MongoDb使用update\(\)命令可以实现替换完成的文档\(数据\)或者一些指定的数据字段.
* Mongodb中的Map\/reduce主要是用来对数据进行批量处理和聚合操作。
* Map和Reduce.Map函数调用emit\(key,value\)遍历集合中所有的记录,将key与value传给Reduce函数进行处理.
* Map函数和Reduce函数是使用Javascript编写的,并可以通过db.runCommand或mapreduce命令来执行MapReduce操作.
* GridFS是MongoDB中的一个内置功能,可以用于存放大量小文件.
* MongoDB允许在服务端执行脚本,可以用Javascript编写某个函数,直接在服务端执行,也可以把函数的定义存储在服务端,下次直接调用即可.
* MongoDB支持各种编程语言:RUBY,PYTHON,JAVA,C++,PHP,C\#等多种语言.
* MongoDB安装简单.

**下载地址**:[http:\/\/www.mongodb.org\/downloads](http://www.mongodb.org/downloads)

**相关工具**:

**监控**

* Munin

* Gangila

* Cacti


**GUI**
* Fang of Mongo – 网页式,由Django和jQuery所构成.
* Futon4Mongo – 一个CouchDB Futon web的mongodb山寨版.
* Mongo3 – Ruby写成.
* MongoHub – 适用于OSX的应用程序.
* Opricot – 一个基于浏览器的MongoDB控制台, 由PHP撰写而成.
* Database Master — Windows的mongodb管理工具
* RockMongo — 最好的PHP语言的MongoDB管理工具,轻量级,支持多国语言.



