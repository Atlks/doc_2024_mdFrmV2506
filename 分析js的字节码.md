分析js的字节码


使用Chrome DevTools查看字节码
打开Chrome浏览器并导航到任意网页或 about:blank。
打开DevTools：按 F12 或 Ctrl+Shift+I （Windows/Linux）或 Cmd+Option+I （Mac）。
切换到控制台(Console)标签。
启用字节码日志记录：在控制台中输入以下命令并按回车键：

javascript


Copy code


%EnableCodeLoggingForTesting();


运行你的示例代码：在控制台中输入你的JavaScript代码：

javascript


Copy code


let arr = [];
arr.push(42);


查看生成的字节码日志：在控制台中输入以下命令并按回车键：

javascript


Copy code


%GetCodeLoggingForTesting();


你将看到一大堆字节码输出，其中包含你的代码生成的字节码

