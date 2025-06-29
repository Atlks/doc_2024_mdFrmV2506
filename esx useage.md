sieze..  es 400M  
res use....mem 200m


## disable http secury

# Enable security features
xpack.security.enabled: false

## Start Elasticsearch
Run bin/elasticsearch (or bin\elasticsearch.bat on Windows) to start Elasticsearch with security enabled.

使用 Elasticsearch
## 检查是否启动成功：

C:\Users\uuu>curl -X GET "localhost:9200"
{
  "name" : "DESKTOP-B7SOH54",
  "cluster_name" : "elasticsearch",
  "cluster_uuid" : "cz2Wc3BnTdSV2n4oZfJV2g",

在浏览器中访问 http://localhost:9200，如果看到 JSON 格式的响应，说明 Elasticsearch 启动成功。
索引数据：

使用 curl 或 Postman 发送 HTTP 请求。以下是使用 curl 创建索引的示例：
bash
Copy code
curl -X PUT "localhost:9200/my_index"
添加文档：

向索引中添加文档：
bash
Copy code
curl -X POST "localhost:9200/my_index/_doc/1" -H 'Content-Type: application/json' -d '{  "title": "tt",  "content": "ccccc."}'
curl -X POST "http://localhost:9200/my_index/_doc/1" -H "Content-Type: application/json" -d "{ \"id\": \"id1\",\"v\": \"v1\"  }"
curl -X POST "http://localhost:9200/my_index/_doc/2" -H "Content-Type: application/json" -d "id=2,v=v2"

查询数据：

查询索引中的文档：
bash
Copy code
curl -X GET "localhost:9200/my_index/_search?q=Elasticsearch"


##。。。。。。
"localhost:9200/my_index/_doc/1"：

localhost:9200：这是 Elasticsearch 服务的地址和端口，表示它在本地运行。
my_index：这是你要添加文档的索引名称。如果索引不存在，Elasticsearch 会自动创建一个。
_doc：这是文档类型（在较新的 Elasticsearch 版本中，文档类型通常被简化为 _doc）。
1：这是文档的 ID。你可以为每个文档指定一个唯一的 ID，用于后续的更新或删除操作。




## RestHighLevelClient1的使用
##  执行搜索请求
            SearchResponse searchResponse = RestHighLevelClient1.search(searchRequest, RequestOptions.DEFAULT);

## get by id

 client.get(request);