Java等避免null npe空安全措施


在 Java 中，避免 null 的关键是防御性编程、工具支持和良好的设计实践。优先使用现代化特性（如 Optional 和注解）以及静态分析工具，可以大大减少空指针异常的风险。

默认值机制
必须要有申明值，不能为null


2.1 Optional 类（推荐）
从 Java 8 开始，引入了 java.util.Optional，用来表示可能为空的值。
废除null，使用opt代替


.2 使用 @NonNull 注解 or  null空值检测
使用第三方库（如 Lombok 或 JSR-305），标注方法参数和返回值，表明它们不应为 null。
如果传递 null 值，Lombok 会在运行时抛出 NullPointerException。


Chek null  if Null
1. 检查输入是否为 null
在使用对象之前，明确地检查是否为 null。


2.3 使用 Objects 类中的方法
Java 提供了 Objects 工具类来处理 null 值。

3.1 使用不可变对象
通过不可变对象设计，确保对象在创建后不会变为 null。
避免使用 null，通过不可变设计增强空安全性
3.2 参数校验
在方法或构造函数中使用断言或异常进行参数校验。
3.3 避免链式调用
链式调用容易引发 NullPointerException，可以使用空安全检查或 Optional 替代


// 不推荐 String value = obj.getParent().getChild().getValue(); // 推荐 Optional<String> value = Optional.ofNullable(obj) .map(Parent::getChild) .map(Child::getValue);


Try 模式

4. 工具支持  静态分析
4.1 静态分析工具
使用工具如 SpotBugs、FindBugs 或 SonarQube 检测可能的 null 问题。
4.2 静态类型检查器
使用 Checker Framework 的 @Nullable 和 @NonNull 注解，进行编译时检查。

9. 尽量避免 null 的设计
从设计角度入手，减少返回 null 的情况：

返回空集合而不是 null：
返回默认值而不是 null：

一些现代工具（如 Lombok）可以简化 null 检测： @NonNull
