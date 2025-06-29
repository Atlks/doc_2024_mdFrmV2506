Kotlin 语法  编程语言语法总结




特性 语法特性
Script file 模式支持 

变量、常量声明 全局变量


otlin中常量用val声明，变了用var声明，关键字在前面，类型以冒号:隔开在后面，也可以省略直接赋值，类型后带问号?表示可为空类型(默认空安全)。

默认文件里面变量就是全局


流程控制语句  if for 条件when
if...else 正常使用，不过移除了switch用更强大的when替代，when子式可以是常量、变量、返回数值的表达式、返回Boolean值的表达式，强大到用来替换if...else if
// 测试值 x = 0, -1, 1, 2, 3, 6, 10var x = 10
when (x) {
    //常量
    2 -> println("等于2")
    //数值表达式
    if (x > 0) 1 else -1 -> println("大于0并等于1，或小于0并等于-1")
    //Boolean类型表达式
    in 1..5 -> println("范围匹配1-5")
    !in 6..9 -> println("不是6-9")
    is Int -> println("类型判断")
    else -> println("else")}// 代替if...else if
when{
    x > 6 && x <= 10  ->  println("大于6小于等于10")
    x < 6 -> println("小于6")
    else -> println("else")}
 字符串模板

在Java中拼接字符串的代码可读性都很差，在Kotlin字符串拼接变得非常简洁，只需用$后面加上参数名，复杂的参数要加上{}


空判断 NULL检查机制

Kotlin的空安全设计对于声明可为空的参数，在使用时要进行空判断处理，有两种处理方式，字段后加!!像Java一样抛出空异常，另一种字段后加?可不做处理返回值为 null或配合?:做空判断处理

10. 区间
区间表达式由具有操作符形式 .. 的 rangeTo 函数辅以 in 和 !in 形成。
 lambda 表达式来过滤
8. 类型检测及类型转换

重要api
屏幕输出  println（）


FP支持函数传递  
函数传递 Lambda模式 n 或方法引用

方法引用   ：：xx()

{xxx()}

函数参数
 kFunction0: () -> Unit



