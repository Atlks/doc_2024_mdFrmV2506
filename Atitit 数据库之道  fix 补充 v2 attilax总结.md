Atitit 数据库之道  fix 补充 attilax总结

数据库类型  kv nosql 文档型

存储结构ini json  json+行   excel zip文件

存储引擎  hot iot

索引系统 免索引模式 分区  

分区系统

Orm 自动化建库建表加字段建立索引

数据完整性通常由三种形式： 
1. 实体完整性：即表中有一个主键。 
2. 域完整性：数据值满足指定的条件。 
3. 参照完整性：表示与参照表的关系和数据约束，即外键。

1.实体完整性
实体完整性在MySQL中表现为设置主键约束和唯一性约束，即primary key与unique key。这两个约束均会在数据库中创建对应的索引。
2.域完整性
域完整性又称为用户自定义完整性，保证数据值满足用户指定的条件。在InnoDB中域的完整性通过以下几点：Default（数据的默认值），not null（数据非空）。在InnoDB中不支持check约束，可以通过enum类型变量去约束离散的值，或者设置触发器来检查数据合法值。
3.参照完整性
参照完整性通过外键实现，并会创建索引。

