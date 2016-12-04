# 创建删除数据库

**创建数据库**

* use dbname - 如果数据库不存在则创建,否则切换到该数据库
* db - 查看当前数据库
* show dbs - 查看所有数据库,没有数据的数据库不会显示
* db.test.insert\({"name":"王土水"}\) - 插入数据,如果没有数据库,会默认插入到test测试数据库

**删除数据库**

* show dbs
* use dbname
* db.dropDatabase\(\)
* db.collection.drop\(\)

