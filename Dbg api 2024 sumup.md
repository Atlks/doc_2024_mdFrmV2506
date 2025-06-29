Dbg api 2024 sumup




查看变量

Var_dump
Print_r



显示当前调用函数和参数
func_get_args
获取程序的整个堆栈调用关系
StackTrace st = new StackTrace(true); 就可以获取程序的整个堆栈调用关系的列表信息
debug_backtrace — 产生一条回溯跟踪(backtrace)
debug_print_backtrace — 打印一条回溯。


自动捕获全局异常 和异步异常

error_reporting(E_ALL ^ (E_NOTICE | E_WARNING));

error_log 
set_error_handler('error_handler142');  //this only for log dbg ,,,if local dbg ,,console dbg is more easy
register_shutdown_function('shutdown_hdlr');
set_exception_handler('ex_hdlr');
日志记录api
Php hilev api dbg api.docx
