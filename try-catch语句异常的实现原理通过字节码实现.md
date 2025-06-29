try-catch语句通过字节码实现


Try语句结束后一个jmp判断即可。如果有异常，处理异常。。

应该是 任何一个语句结束后一个jmp判断即可比较好吧
全文的字节码显示如下：
0:  ldc.i4.10       // 将值 10 推送到操作数堆栈
5:  ldc.i4.0       // 将值 0 推送到操作数堆栈
9:  div             // 执行除法操作
10: stloc.0       // 将结果存储到局部变量 0 中
15: jmp     (IL_001f) 0x1f (15) // 如果没有异常，则跳转到指令 15
20: ldloc.0       // 将局部变量 0 的值加载到操作数堆栈
25: callvirt instance class [mscorlib]System.Exception
2f: newobj instance class [mscorlib]System.DivideByZeroException
34: stloc.1       // 将异常对象存储到局部变量 1 中
39: br.s     (IL_0043) 0x43 (4) // 跳转到指令 43
44: ldc.i4.s       (int16)58 // 将错误信息 "除法错误：" 推送到操作数堆栈
49: ldloc.1       // 将局部变量 1 的值加载到操作数堆栈
54: callvirt instance method [mscorlib]System.Exception::get_Message()
59: callvirt instance method [mscorlib]System.String::Concat(string)
64: stloc.2       // 将结果字符串存储到局部变量 2 中
69: ldloc.2       // 将局部变量 2 的值加载到操作数堆栈
74: callvirt instance method [mscorlib]System.Console::WriteLine(string)
79: ret       // 返回方法
异常表：
在字节码中，还有一个异常表用于存储有关可能抛出的异常信息。异常表包含以下信息：
起始指令：表示可能出代码块的起始位置。
结束指令：表示可能提出出代码的结束位置。
处理程序指令：表示用于处理代码块的起始位置。
异常类型：表示可能抛出的异常类型。
截至本文撰稿时，表格如下：
0: (0x0000-0x000f) -> 0x0020 (catch) [mscorlib]System.DivideByZeroException
总结
C# 中的try-catch语句通过字节码实现。存储有关可能出现的问题的信息，并指示异常时处理方式。
tuneshare
more_vert

