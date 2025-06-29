Mysql与数据文件  库表




InnoDB：数据和索引通常存储在一个 .ibd 文件中，默认每个表一个文件。


总结
MySQL 7.x：默认值为 OFF，即数据和索引存储在共享的系统表空间中。
MySQL 8.x：默认值为 ON，即每个表的数据和索引存储在独立的 .ibd 文件中。
如果你使用的是 MySQL 8.x 或更新版本，innodb_file_per_table 已经默认启用，可以直接享受其带来的好处。如果你使用的是 MySQL 7.x 或更早版本，则需要手动启用该选项。
4o mini

