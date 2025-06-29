Lucene的prblm

User troulbe
No good gui tool..luke err..


Uniq idx def not 

方法 2: 更新文档
如果你希望在文档存在时更新它，而不是简单地跳过，你可以使用 updateDocument 方法：
java
Copy code
if (documentExists("id", id)) {
    indexWriter.updateDocument(new org.apache.lucene.index.Term("id", id), doc)

