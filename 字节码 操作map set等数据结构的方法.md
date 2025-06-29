字节码 操作map set等数据结构的方法


Python直接有单独指令


。Net使用newobj方法。。


添加元素 。Net 使用  callvirt 调用add方法


获取 Hashtable 元素
csharp
Copy code
object value = hashtable["key"];


Callvirt   get_Item


Remv


Callvirt  .Hashtable::Remove



·  newobj 指令用于创建新的对象。
·  callvirt 指令用于调用方法，包括 Add、get_Item、Remove 和 ContainsKey 方法。
·  ldloc 和 stloc 指令用于加载和存储局部变量。



