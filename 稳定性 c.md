稳定性 c# 


异步和同步 设置全局捕获不可的，只是会记录日志，但会自动退出。

在 .NET 中，当未处理的异常发生时，默认行为是终止应用程序。即使你设置了 AppDomain.CurrentDomain.UnhandledException 事件来捕获未处理的异常，它依然会导致应用程序退出。
要防止应用程序在发生未处理的异常时退出，你需要采取一些特殊措施。这里有一些方法可以考虑：
1. 使用异常处理器和异常恢复
为关键部分代码添加异常处理器（try-catch），并在发生异常时尝试恢复应用程序状态
. 处理 AppDomain.CurrentDomain.UnhandledException 并创建一个新的线程
在 UnhandledException 事件处理程序中，创建一个新的线程来恢复应用程序的执行：
csharp
Copy code
AppDomain.CurrentDomain.UnhandledException += (sender, e) =>
{
    Console.WriteLine($"Unhandled exception: {e.ExceptionObject}");

    // 延迟启动一个新的线程
    new System.Threading.Thread(() =>
    {
        // 恢复应用程序逻辑
        Console.WriteLine("Application is recovering...");
        // Restart or recover logic here
    }).Start();
};



使用 TaskScheduler.UnobservedTaskException 处理异步异常
对于异步操作，可以使用 TaskScheduler.UnobservedTaskException 事件来捕获未观察到的异常：
csharp
Copy code
TaskScheduler.UnobservedTaskException += (sender, e) =>
{
    Console.WriteLine($"Unobserved exception: {e.Exception}");
    e.SetObserved();  // 阻止异常传播
};



4. 使用自定义主循环
可以创建一个自定义的主循环来捕获所有未处理的异常，从而防止应用程序退出。
bool running = true; while (running) { try { // Your main application logic here } catch (Exception ex) { Console.WriteLine($"Exception in main loop: {ex.Message}"); // 处理异常并决定是否继续运行 running = ShouldContinueRunning(ex); } }。
