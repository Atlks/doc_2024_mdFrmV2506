jdk里程碑版本的发布时间和重大新特性有哪些
ChatGPT said:
ChatGPT
JDK（Java Development Kit）是 Java 编程语言的官方开发工具包，定期发布新版本。每个版本通常包括新的功能、性能改进和修复。以下是 JDK 的主要里程碑版本及其重大新特性和发布时间：

JDK 1.0
发布时间: 1996年1月
重大新特性:
Java语言的初始版本
包括基本的类库（如 java.lang、java.util、java.io）
引入了基本的语言特性，如面向对象编程、垃圾回收和线程
JDK 1.1
发布时间: 1997年2月
重大新特性:
增强的 AWT（Abstract Window Toolkit）支持
引入了 JDBC（Java Database Connectivity）
事件监听模型改进
内部类支持
JDK 1.2 (Java 2)
发布时间: 1998年12月
重大新特性:
引入了 Swing（更先进的图形用户界面工具包）
引入了 Collections Framework
支持 JIT 编译（即时编译）
引入了 Java Plug-in
JDK 1.3
发布时间: 2000年5月
重大新特性:
改进的性能和稳定性
引入了 Java Naming and Directory Interface (JNDI)
引入了 Java Sound API
引入了 HotSpot JVM
JDK 1.4
发布时间: 2002年2月
重大新特性:
引入了 NIO（New I/O）
引入了 Logging API
引入了 XML 支持（通过 JAXP）
异常链改进（Throwable.getCause()）
JDK 1.5 (Java 5)
发布时间: 2004年9月
重大新特性:
泛型支持
增强的 for 循环（for-each）
枚举类型
注解（Annotations）
自动装箱和拆箱
线程的 java.util.concurrent 包
JDK 1.6 (Java 6)
发布时间: 2006年12月
重大新特性:
改进的 Java Compiler API
引入了脚本支持（通过 Java Compiler API）
增强的性能和启动速度
改进的 GUI 支持（Swing 和 Java2D）
更强大的 Web 服务支持
JDK 1.7 (Java 7)
发布时间: 2011年7月
重大新特性:
引入了 try-with-resources 语法
引入了二进制字面量和改进的字符串处理
引入了 Fork/Join 框架
支持动态语言（通过 invokedynamic 指令）
引入了 NIO 2.0
JDK 1.8 (Java 8)
发布时间: 2014年3月
重大新特性:
引入了 Lambda 表达式
引入了 Streams API
引入了新的日期和时间 API（java.time）
引入了默认方法和静态方法接口
引入了 Optional 类
JDK 9
发布时间: 2017年9月
重大新特性:
引入了模块系统（Project Jigsaw）
改进的 JShell（Java Shell）
改进的 Javadoc 支持
更强的性能和垃圾回收改进
JDK 10
发布时间: 2018年3月
重大新特性:
局部变量类型推断（var）
引入了新的垃圾回收器（G1 GC 改进）
线程本地变量（Thread-local Handshakes）
JDK 11
发布时间: 2018年9月
重大新特性:
引入了新的 HTTP 客户端 API
支持 Flight Recorder（性能分析工具）
弃用了 Java EE 和 CORBA 模块
长期支持（LTS）版本
JDK 12
发布时间: 2019年3月
重大新特性:
引入了 Shenandoah 垃圾回收器
提升 JVM 诊断工具
改进的 Switch 表达式（实验性）
JDK 13
发布时间: 2019年9月
重大新特性:
引入了文本块（Text Blocks，实验性）
引入了 ZGC（Z Garbage Collector）的一些新特性
JDK 14
发布时间: 2020年3月
重大新特性:
引入了记录类（Record Types，预览功能）
引入了 NullPointerException 提示
提升 ZGC 的功能
JDK 15
发布时间: 2020年9月
重大新特性:
引入了封闭类（Sealed Classes，预览功能）
引入了文本块（Text Blocks，标准功能）
进一步改进 ZGC 和 Shenandoah 垃圾回收器
JDK 16
发布时间: 2021年3月
重大新特性:
引入了 JEP 394: 移除实验性的 Solaris 和 SPARC 架构支持
引入了 JEP 395: 记录类（Record Types，标准功能）
引入了 JEP 396: ZGC 的新的 Concurrent Class Unloading
JDK 17
发布时间: 2021年9月
重大新特性:
长期支持（LTS）版本
引入了 JEP 389: 外部内存访问 API
引入了 JEP 411: Deprecate 远程方法调用
引入了 JEP 391: Sealed Classes（正式特性）
JDK 18
发布时间: 2022年3月
重大新特性:
引入了 JEP 396: Unicode 15.0 支持
引入了 JEP 394: 卸载的类加载器
引入了 JEP 421: Pattern Matching for switch（预览功能）
JDK 19
发布时间: 2022年9月
重大新特性:
引入了 JEP 405: Record Patterns（预览功能）
引入了 JEP 424: Foreign Function & Memory API（预览功能）
引入了 JEP 432: Pattern Matching for switch（正式功能）
JDK 20
发布时间: 2023年3月
重大新特性:
引入了 JEP 429: Scoped Values（预览功能）
引入了 JEP 428: Pattern Matching for switch（增强功能）
JDK 21
发布时间: 2023年9月
重大新特性:
引入了 JEP 423: Foreign Function & Memory API（正式功能）
引入了 JEP 437: Record Patterns（正式功能）
引入了 JEP 440: Scoped Values（预览功能）
这些里程碑版本展示了 Java 从早期的基本功能发展到现在支持现代编程特性的历程。每个版本都引入了新的功能、改进和性能优化，以支持开发者在不同领域中的需求。