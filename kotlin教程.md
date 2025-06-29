kotlin教程



全局变量/顶级变量
在 Kotlin 中，全局变量是在程序顶部和所有函数外部声明的变量，类似于 C 和 C++。局部变量只能在声明它的特定块中使用。全局变量可以在所有函数中使用。
全局变量示例程序
// Global Variables / Top-level Variables Kotlin example program// Variable Kotlin Programs , Basic Kotlin Programs// Declared Global Variable `Int` type is inferredvar x = 100fun fn() { 
    x = x + 100 
}fun main(args: Array<String>) {
    println("X Value : $x")
    
    fn()
    
    println("X Value : $x")
}

