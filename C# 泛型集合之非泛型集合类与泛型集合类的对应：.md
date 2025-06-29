C# 泛型集合之非泛型集合类与泛型集合类的对应：
ArrayList对应List
HashTable对应Dictionary
Queue对应Queue
Stack对应Stack
SortedList对应SortedList

泛型集合List<T>
　　泛型最重要的应用就是集合操作，使用泛型集合可以提高代码重用性，类型安全和更佳的性能。
　　List<T>的用法和ArrayList相似，List<T>有更好的类型安全性，无须拆，装箱。

List泛型集合：
先看下IEnumerable、ICollection、IList、List继承关系。（这里带有泛型，非泛型也是一样的关系）
功能多少排序：List > IList > ICollection > IEnumerable。
泛型集合List<T>
　　泛型最重要的应用就是集合操作，使用泛型集合可以提高代码重用性，类型安全和更佳的性能。
　　List<T>的用法和ArrayList相似，List<T>有更好的类型安全性，无须拆，装箱。
List<T>和ArrayList的区别
      List<T>和ArrayList的相同点：添加元素、删除元素、通过索引访问元素方法相同。
　　List<T>和ArrayList的不同点：
ArrayList可以添加任意类型元素；List<T>对添加的元素具有类型约束；
ArratList添加时装箱，读取时拆箱；List<T>不需要装箱，拆箱操作；‘



第二 ：HashTable(非泛型集合)对应Dictionary（泛型集合）
Hashtable 和 Dictionary <K, V> 类型


