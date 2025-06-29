灵活的方式来遍历和修改JSON结构，
解析JSON字符串：使用JsonDocument.Parse方法将JSON字符串解析为只读的JsonDocument对象。


转换为可变结构：为了修改JSON数据，我们首先将JsonDocument转换为可变的Dictionary<string, object>结构。


遍历和修改字典：递归遍历字典结构，查找并修改需要的属性。在这个示例中，找到age属性并将其值增加1。


序列化回JSON字符串：使用JsonSerializer.Serialize方法将修改后的字典结构序列化回JSON字符串。

这种方法提供了一种灵活的方式来遍历和修改JSON结构，但需要注意的是，处理复杂的JSON结构时，需要小心处理数据类型的转换和递归调用。




