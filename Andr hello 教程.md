Andr hello 教程



Instl andr stuido


新建一个Android项目
重新打开Android Studio，新建一个Android项目吧，添加一个默认的MainActivity
——像以前一样即可。
配置之后，等sync完成，就可以运行了~ （如果你sync失败或者耗时过长，赶紧检讨一下自己有没有科学上网？）


已经自动下载了sdk和安卓模拟器，自动运行、





WebView 项目通常遵循以下目录结构：
- app/
  |- src/
  |  |- main/
  |     |- java/
  |     |  |- com.example.app/           	# 应用的代码
  |     |  |  |- MainActivity.java       	# 主Activity文件
  |     |
  |     |- res/
  |     |  |- layout/                    	# 布局文件
  |     |  |  |- activity_main.xml
  |     |  |
  |     |  |- values/                    	# 值资源文件
  |     |  |  |- strings.xml			 	# 字符串资源文件
  |     |
  |     |- AndroidManifest.xml   			# 应用程序清单文件
  |
  |     |- assets/                        	# WebView使用的本地资源
  |     |  |- index.html                  	# WebView入口HTML文件
  |     |  |- css/                        	# CSS样式文件
  |     |  |- js/                         	# JavaScript脚本文件
  |     |  |- images/                     	# 图片文件
  |     |- ...
  |- build.gradle.kts                     	# 项目的Gradle构建配置文件
  |- ...



2. AndroidManifest.xml

重要: AndroidManifest.xml 是 Android 应用程序的 核心配置文件，它描述了应用程序的基本信息、组件、权限和行为等。在开发 Android 应用程序时，清单文件的正确配置和使用非常重要，它直接影响应用程序的功能和行为。
<?xml version="1.0" encoding="utf-8"?><manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools">
    
    <!-- 权限声明：通过 <uses-permission> 元素，你可以声明应用程序需要的权限。Android 操作系统会在安装应用程序时向用户展示所请求的权限，并在用户同意后授予应用程序相应的权限。 -->
    <uses-permission android:name="android.permission.INTERNET" />
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    <uses-permission android:name="android.permission.ACCESS_WIFI_STATE" />
    
    <!-- <application> 元素用于定义应用程序的全局配置和属性 -->
    <application
        android:allowBackup="true"
        android:dataExtractionRules="@xml/data_extraction_rules"
        android:fullBackupContent="@xml/backup_rules"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.MyWebview"
        tools:targetApi="31">
        
        <!-- <activity> 元素用于声明应用程序的活动（Activity）。每个活动都需要在清单文件中进行声明，以便在应用程序中使用
android:name: 指定活动的类名(默认MainActivity.java)
android:theme：指定活动的主题样式
-->
        <activity
            android:name=".MainActivity"
            android:exported="true"
            android:label="@string/app_name"
            android:theme="@style/Theme.MyWebview">
            
            <!--  用于指定一个活动（Activity）作为应用程序打开时的主要入口点, 不可有多个, 多个的话安装app时桌面会出现多个应用图标  -->
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
            
        </activity>
        
    </application>
</manifest>


Juti step

添加WebView组件(layout.xml)   MyApplication\app\src\main\res\layout\activity_main.xml

 如果没有这个文件的话 新家 
C:\Users\User\AndroidStudioProjects\MyApplication\app\src\main\res\layout\activity_main.xml


<?xml version="1.0" encoding="utf-8"?>
<WebView android:id="@+id/webView1"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
  
    xmlns:android="http://schemas.android.com/apk/res/android" />




修改启动类 MainActivity.kt



C:\Users\User\AndroidStudioProjects\MyApplication\app\src\main\java\com\example\myapplication\MainActivity.kt


class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        //这里管理起来gui.xml文件。。
        setContentView(R.layout.activity_main)

        val webView1: WebView =findViewById(R.id.webView1)
        //是否与JavaScript交互
        webView1.settings.javaScriptEnabled = true
//是否打开Dom本地存储
        webView1.settings.domStorageEnabled = true
        webView1.loadUrl("https://www.baidu.com")


    }
}


Load local htm

Android WebView加载本地资源文件（html、css、js）
1、在main目录下创建一个名为assets的文件夹。
右键main->new->Directory->assets
2、assets文件夹下 ，否则html文件不能加载js和css文件。
3、将html、css、js文件都放在qk目录下，然后原生页面用
 webView.loadUrl("file:///android_asset/test.html");
来加载html文件，html文件中引用js、css文件直接用相对路径即可

jide这里一定使用 android_asset。。。不是 android_assets




Ref


Android WebView 一孔之见（上） - 掘金
