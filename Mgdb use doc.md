Mgdb use doc





普通查询 单字段

// 查询文档
FindIterable<Document> iterable = collection.find(new Document("name", "Alice"));
for (Document doc : iterable) {
    System.out.println("Found document: " + doc.toJson());
}


查询多字段
// 构建查询条件 Document query = new Document("age", new Document("$gt", 25)) .append("name", "Alice");

聚合查询 

// 创建聚合管道 var pipeline = Arrays.asList( Aggregates.match(Filters.eq("area", "地区")), // 过滤条件 Aggregates.group(null, Accumulators.sum("smx", "$amt")) // 聚合求和 );

// 执行聚合查询 try (MongoCursor<Document> cursor = collection.aggregate(pipeline).iterator()) {
聚合查询分组聚合grpby

// 创建聚合管道 // 1. 分组聚合: 按 customerId 分组并计算总金额 var pipeline = Arrays.asList( Aggregates.group("$customerId", Accumulators.sum("totalAmount", "$amount")) );
