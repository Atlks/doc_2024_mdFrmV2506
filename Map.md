Map、Filter和Reduce是数组的常用方法 图示法
，可以让你在实现一些数组操作时告别循环，具有很高的实用价值。它们三个的意义大家应该都清楚，有一个十分形象的解释如下：
 

支持lambda表达式的C#也有类似的方法，但不是这样命名的。实现IEnumerable接口的类（如List、HashSet、继承Array的类等）都有如下等价方法：
“Map” => Select方法
“Filter” => Where方法
“Reduce” => Aggregate方法

