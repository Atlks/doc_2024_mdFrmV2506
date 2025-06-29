Lua 的字节码 一共有哪些


Mov load  操作table

GETGLOBAL   SETTABLE 
GETTABLE A B C
将寄存器 R(B) 的表中键为 R(C) 的值加载到寄存器 R(A)。
SETGLOBAL A Bx
将寄存器 R(A) 的值存储到全局变量 G(Bx)。
SETTABLE A B C
将寄存器 R(A) 的表中键为 R(B) 的值设为 R(C)。
NEWTABLE A B C
创建一个新的表，初始化寄存器 R(A)。


运算指令
加减乘除摸指令10个
And or not 


集合操作  len concat
LEN A B
计算寄存器 R(B) 的值的长度，结果存入寄存器 R(A)。
CONCAT A B C
将寄存器 R(B) 到 R(C) 的值连接起来，结果存入寄存器 R(A)。
跳转与比较指令 控制流
Jmp forloop

·  JMP sBx
·  跳转到当前指令的索引加上 sBx。
·  EQ A B C
·  如果寄存器 R(B) 和 R(C) 的值相等，跳过下一条指令。
TEST A C
如果寄存器 R(A) 的值为真（非零），跳过下一条指令
·  FORLOOP A sBx
·  迭代 for 循环，R(A) 是索引，R(A+1) 是终止值，R(A+2) 是步长，跳转到当前指令的索引加上 sBx。

Call  ret
·  CALL A B C
·  调用函数，R(A) 是函数，R(A+1) 到 R(A+B-1) 是参数，结果存储到 R(A) 到 R(A+C-2)。
·  TAILCALL A B C
·  尾调用函数，与 CALL 类似，但没有返回。
·  RETURN A B
·  返回函数，R(A) 到 R(A+B-2) 是返回值。
SETLIST A B C
设置表 R(A) 中的字段，从 R(A+1) 开始，总数为 B。
·  CLOSURE A Bx
·  创建一个闭包，存储到寄存器 R(A)。
·  VARARG A B
·  变参函数，获取传入的变长参数，存储到寄存器 R(A) 到 R(A+B-1)。

4. 比较操作
TestEqual: 比较栈顶和累加器中的值是否相等。
TestLessThan: 比较栈顶的值是否小于累加器中的值。
TestGreaterThan: 比较栈顶的值是否大于累加器中的值。


