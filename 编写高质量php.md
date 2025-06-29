编写高质量php





declare(strict_types


如何使得编写php bug更少,除了 declare(strict_types=1); 还有什么方法
ChatGPT said:
ChatGPT
为了减少 PHP 代码中的错误，除了启用 declare(strict_types=1); 之外，以下是一些常用的最佳实践和工具，可以帮助你减少 bug 并提高代码质量：
1. 使用静态类型声明
类型提示：PHP 7 和 8 允许为函数参数和返回值声明类型（如 int, string, array），这可以确保函数使用时类型匹配。


静态检查工具

静态分析工具：结合工具如 PHPStan 和 Psalm，可以在运行代码之前发现潜在的类型错误、未使用的代码、类型不匹配等问题。
PHPStan：专注于类型安全检查。
Psalm：功能更强，支持类型推导和多种高级类型检查
vendor/bin/phpstan analyse  ./src  --level 10



Ide工具

使用更严格的错误报告

开启所有错误报告：在开发环境中，确保 PHP 报告所有错误，这样可以及时发现潜在问题。


php


Copy code


error_reporting(E_ALL);ini_set('display_errors', '1');



日志记录：即使在生产环境中，也应配置日志记录，以便在出现问题时能追踪到错误的来源

单元测试和自动化测试

PHPUnit：使用 PHPUnit 编写单元测试，并确保你的代码在修改后仍然能够正常工作。单元测试可以帮助你在更改代码时确保没有引入新的 bug。


使用容错设计 try cathch

错误处理：在关键操作中使用异常处理（try-catch）来捕获错误并提供有用的错误消息，而不是让程序崩溃。

使用自定义异常类来处理特定类型的错误，并提供清晰的错误日志
使用其他静态语言编写并翻译
总结
通过结合以下方法，你可以大大减少 PHP 代码中的错误：
使用静态类型声明和 declare(strict_types=1);。
使用静态分析工具（如 PHPStan 或 Psalm）。
配置 PHP 错误报告。
使用单元测试和代码覆盖工具。
遵循编码标准和设计模式。
避免使用全局变量，减少副作用。
定期重构代码，保持代码简洁清晰。
使用异常处理，确保容错设计。
进行代码审查和持续集成。
这些实践有助于减少 bug 并提高代码的稳定性和可维护性。

