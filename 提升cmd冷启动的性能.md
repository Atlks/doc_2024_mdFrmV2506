提升cmd冷启动的性能

合并jar
减少console的读取
指定classname防止搜索

纯粹的常驻内存快，但是不稳定。。Cmd冷启动有太慢

或者可以结合起来，api自动每隔十分钟重启一次，即可。。

换用go即可

·  冷启动速度：Go 的冷启动速度通常最快，其次是 TypeScript，C# 稍慢，而 Java 在所有语言中启动时间最长。
·  选择语言：在对冷启动速度要求极高的场景（如无服务器架构）中，Go 和 TypeScript 是较好的选择，而 Java 和 C# 在企业级应用中仍有其优势，特别是在复杂的业务逻辑和生态系统中。

