Win install linux 





四、连接桌面
先安装VNC
Sudo  apt-get install tightvncserver

运行以下命令，启动VNC。
 
Sudo vncserver


第一次启动需要设置VNC的登录密码，输入VNC登录密码和确认密码，并在以下提示中输入n，并按Enter。2558

重要
如果您自定义的密码位数大于8位，系统默认只截取前8位作为您的VNC登录密码。

然后使用vnc客户端连接即可查看桌面，如果显示端口是4那么在客户端连接的就是127.0.0.1:4 (每个人的不一样，可自行修改，一般默认是0)


接下来先输入VNC启动命令：
sudo vncserver -geometry 1600x900 :4
 sudo vncserver -geometry 1600x900 :8


Probl m
如果auth不足，需要添加sudo前缀。。


链接vnc


192.168.128.226:7

使用vncserver  得到了桌面序号。。


然后链接的时候冒号后面更的是桌面序号，而不是vnc\端口5901


