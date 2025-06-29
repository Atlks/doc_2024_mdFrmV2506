andr如何真机调试


打开开发者，打开usb dbg 模式

链接。。Andr stuido就显示了设备自动。。。



2. 使用 ADB 安装 APK
如果您已经生成了 APK 文件，并希望手动安装它，可以使用 ADB（Android Debug Bridge）命令来完成：

打开终端或命令提示符：根据您的操作系统打开终端或命令提示符窗口。


导航到 APK 文件所在的目录：使用 cd 命令导航到包含 APK 文件的目录。例如：


bash


Copy code


cd path/to/your/apk



安装 APK：运行以下 ADB 命令来安装 APK：


bash


Copy code


adb install app-release.apk



