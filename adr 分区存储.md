分区存储（Scoped Storage）的规则
ChatGLM

引用
分区存储（Scoped Storage）是Android 10（API 级别 29）引入的一项安全特性，旨在更好地保护用户数据和隐私。以下是分区存储的一些主要规则和特点：

默认存储位置：

应用应该使用系统提供的目录来存储文件，例如getExternalFilesDir()和getFilesDir()。这些目录下的文件默认只对应用自身可见。

访问权限：

应用不再需要READ_EXTERNAL_STORAGE和WRITE_EXTERNAL_STORAGE权限来访问自己创建的文件。
如果应用需要访问其他应用的文件或共享的媒体文件，它必须请求相应的权限。

媒体集合访问：

应用可以使用MediaStore API 来访问用户媒体集合中的文件，如照片、视频和音频，而无需请求存储权限。
应用可以使用DocumentsContract API 来访问用户选择的特定文件。

共享存储访问：

应用可以访问共享存储中的特定目录，如Downloads、Documents和Pictures，但需要用户通过文件选择器进行授权。

请求权限：

如果应用需要访问其他应用的文件或共享存储中的文件，它必须使用ACTION_OPEN_DOCUMENT或ACTION_CREATE_DOCUMENT意图来请求用户选择文件。

迁移现有应用：

对于在Android 10之前发布的现有应用，系统会默认允许它们继续使用传统存储模型，但推荐开发者迁移到分区存储。
开发者可以通过在AndroidManifest.xml中设置requestLegacyExternalStorage属性为true来请求临时使用传统存储模型。

透明度：

用户可以通过系统设置查看哪些应用正在访问他们的存储空间。
以下是分区存储的一些具体实现规则：
私有目录：应用可以自由读写自己私有目录下的文件，无需任何权限。
共享目录：应用需要用户通过文件选择器明确授权才能访问共享存储中的文件。
媒体集合：应用可以使用MediaStore API 来访问媒体文件，但需要遵循系统的文件访问规则。
存储访问框架：应用可以使用存储访问框架（SAF）来让用户选择文件或目录进行访问。
开发者应该更新他们的应用以适应分区存储的规则，这通常涉及到以下步骤：
检查应用是否正确地使用了私有目录来存储文件。
使用MediaStore API 来访问媒体文件。
使用Storage Access Framework（SAF）来访问用户选择的文件。
如果需要，请求用户授权来访问特定的共享文件或目录。
在Android 11（API 级别 30）及更高版本中，分区存储的规则进一步加强，例如对getExternalFilesDir()目录的访问也受到了限制。因此，开发者需要持续关注Android存储政策的更新，并确保他们的应用与之保持兼容。

