Smp bp  use smp cls tuple



C# Tuple（元组）
Tuple<T>类是在 .NET Framework4.0 中引入的。元组是一种包含不同数据类型的元素序列的数据结构。它可以用于需要数据结构来保存具有属性的对象，但又不想为其创建单独类型的情况。
语法：
Tuple<T1, T2, T3, T4, T5, T6, T7, TRest>
一个元组最多只能包含八个元素。当您尝试包含八个以上的元素时，它将产生编译器错误。
var numbers = Tuple.Create(1, 2, 3, 4, 5, 6, 7, 8);






用元组（System.ValueTuple） 原创

CSDN博客
https://blog.csdn.net › caimouse › article › details

佛历2565年10月27日 — 在没有使用元组之前，要想在C#里返回多个值，是比较麻烦一些。 不外采用的方案就是参数里使用out来声明多个字段，或者定义一个结构来作为返回值，但是直接



ValueTuple 是在 C# 7 中被引入，它主要用来解决 Tuple 的两个问题。
解决语义化问题，在之前你只能通过 Item1,Item2, ... 的方式进行元素访问
解决性能问题，因为 ValueTuple 是一个轻量级的值类型
这篇文章将会讨论 ValueTuple 是什么及如何使用。
ValueTuple 和 Tuple
ValueTuple 是一个轻量级的值类型，并支持强命名，而 Tuple 是一个引用类型，总的来说，ValueTuple 要比 Tuple 拥有更高的性能，Tuple 中的属性是只读的，也就是说一旦创建好之后就不能进行变更了，而 ValueTuple 的属性就可以在创建之后进行修改。



2.    表示一组数据
如下创建一个元组表示一个学生的三个信息：名字、年龄和身高，而不用单独额外创建一个类。
var studentInfo = Tuple.Create<string, int, uint>("Bob", 28, 175);
Console.WriteLine($"Student Information: Name [{studentInfo.Item1}], Age [{studentInfo.Item2}], Height [{studentInfo.Item3}]");
3.    从方法返回多个值
当一个函数需要返回多个值的时候，一般情况下可以使用out参数，这里可以用元组代替out实现返回多个值。
4.    用于单参数方法的多值传递
当函数参数仅是一个Object类型时，可以使用元组实现传递多个参数值。

