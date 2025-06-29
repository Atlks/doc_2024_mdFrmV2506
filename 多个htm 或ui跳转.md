多个htm 或ui跳转，如何保持上个页面的数据


Global varl 模式more easy
Static var

使用 Local Storage 或 Session Storage
3. 使用 Cookies

使用 URL 参数



在 Flutter 中，可以使用一些库来实现类似于 Web 的 Local Storage 功能，常用的包括 shared_preferences 和 hive。这些库可以帮助你在应用中存储数据，以便在页面跳转后保持状态。
1. 使用 shared_preferences
shared_preferences 是一个轻量级的存储解决方案，适合存储简单的数据（如字符串、数字和布尔值）
2. 使用 hive
如果你需要存储更复杂的数据结构，hive 是一个无类型的本地数据库，支持更高效的存储。
使用 shared_preferences 或 hive 可以有效地在 Flutter 应用中实现数据存储和页面跳转后保持数据的功能。选择适合你需求的方案。

Navi.push (context,page2) 过去。。

小结
最常用的方法是 Local Storage 和 Session Storage，因为它们简单且不需要修改 URL。选择适合你需求的方法来实现数据的保存和传递。

