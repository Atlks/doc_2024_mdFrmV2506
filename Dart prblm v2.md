Dart prblm



run need device

Maybe file import  flutter pkg..del fluter pkg import just ok...


Io file http is ok

Sqlit some prblm
使用sqlite3模块即可
sqlite3

解压并将 sqlite3.dll 文件放入你的 Dart 项目目录（或任何在 PATH 中的目录）


这个错误通常是因为你在非 Flutter 环境中尝试使用 Flutter 库（例如 sqflite）。sqflite 依赖于 Flutter 的 dart:ui 库，这在标准的 Dart 环境中是不可用的。
要解决这个问题，请确保你在 Flutter 项目中运行代码，而不是纯 Dart 项目。以下是确保正确设置的步骤：

