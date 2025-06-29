Adr 访问文件



MediaStore有哪些 ，，除了 MediaStore.Files
ChatGLM

引用
Android的MediaStore类提供了多种不同的URI来访问设备上的媒体文件。除了MediaStore.Files之外，以下是一些可用的MediaStore类型：

MediaStore.Images - 用于访问设备上的图片文件。

MediaStore.Images.Media.EXTERNAL_CONTENT_URI - 访问外部存储上的图片。
MediaStore.Images.Media.INTERNAL_CONTENT_URI - 访问内部存储上的图片。

MediaStore.Audio - 用于访问设备上的音频文件。

MediaStore.Audio.Media.EXTERNAL_CONTENT_URI - 访问外部存储上的音频文件。
MediaStore.Audio.Media.INTERNAL_CONTENT_URI - 访问内部存储上的音频文件。
MediaStore.Audio.Playlists.EXTERNAL_CONTENT_URI - 访问外部存储上的播放列表。
MediaStore.Audio.Playlists.INTERNAL_CONTENT_URI - 访问内部存储上的播放列表。

MediaStore.Video - 用于访问设备上的视频文件。

MediaStore.Video.Media.EXTERNAL_CONTENT_URI - 访问外部存储上的视频文件。
MediaStore.Video.Media.INTERNAL_CONTENT_URI - 访问内部存储上的视频文件。

MediaStore.Downloads - 用于访问设备上通过下载管理器下载的文件。

MediaStore.Downloads.EXTERNAL_CONTENT_URI - 访问外部存储上的下载文件。
MediaStore.Downloads.INTERNAL_CONTENT_URI - 访问内部存储上的下载文件。

MediaStore.Files - 用于访问设备上的文件，不限于特定媒体类型。

MediaStore.Files.EXTERNAL_CONTENT_URI - 访问外部存储上的所有文件。
MediaStore.Files.INTERNAL_CONTENT_URI - 访问内部存储上的所有文件。
每个MediaStore类型都提供了不同的方法和属性来查询和管理特定类型的媒体文件。例如，你可以通过ContentResolver查询特定目录下的所有图片、音频或视频文件，并对它们执行操作，如读取、修改或删除。使用这些MediaStore URI时，你的应用需要具有相应的权限，如READ_EXTERNAL_STORAGE或WRITE_EXTERNAL_STORAGE。

