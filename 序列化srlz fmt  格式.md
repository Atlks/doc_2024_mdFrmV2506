序列化srlz fmt  格式

序列化是将数据结构或对象状态转换为可存储或传输的格式的过程。常见的序列化格式包括：

Qrystr
Json  html  ini

Markdown 
Xml
Avro:
Apache 的数据序列化系统，主要用于 Hadoop。
示例（定义）:

json


Copy code


{
  "type": "record",
  "name": "Person",
  "fields": [
    {"name": "name", "type": "string"},
    {"name": "age", "type": "int"},
    {"name": "email", "type": "string"}
  ]}



