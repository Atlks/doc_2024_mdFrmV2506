Fltr prblm  namespace not defi

您的build.gradle文件看起来大部分都是正确的，但需要检查或澄清一些事项以确保功能顺利运行：
审查并修复：

命名空间声明：声明的方式namespace几乎是正确的，但在较新版本的 AGP 中，namespace应使用属性指定namespace，而不是使用赋值（=）。可以按如下方式修复此问题：

更新webviewdao  4.0  ok


