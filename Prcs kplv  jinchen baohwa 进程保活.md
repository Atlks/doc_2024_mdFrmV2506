Prcs kplv  jinchen baohwa 进程保活


前经服务注册

1. 前台服务（Foreground Service）
通过将服务设置为前台服务，应用会在系统优先级中获得较高的地位，降低被杀的概率。



8. 白名单优化
引导用户将应用添加到系统的电池优化白名单。
java
Copy code
Intent intent = new Intent(Settings.ACTION_IGNORE_BATTERY_OPTIMIZATION_SETTINGS);
startActivity(intent);
优点：从系统角度降低被杀概率。
缺点：需要用户手动操作，用户可能不配合。

