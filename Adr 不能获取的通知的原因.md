Adr 不能获取的通知的原因


强制取消下通知访问，在打开就可以了。可以dbg跑通了。。。

val intent = Intent("android.settings.ACTION_NOTIFICATION_LISTENER_SETTINGS")
startActivity(intent)

