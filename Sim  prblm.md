Sim  prblm   


接受不到消息问题的解决。。



广播多播算法

有时候使用255.255.255.255不起作业。只对pc之间其作用。。

改为192.169.0.255  局域网广播多播，这下pc可以给手机发消息了。。但手机依然不能发给pc

最后使用多播算法，循环给所有 192....0--255 发送消息这下可以了。。。

//mlt boad
        for(int i=1;i<=255;i++){
          for(int pt=28888;pt<=28888;pt++) {
          //  sendMsg(_controllerTextField.text, "255.255.255.255", i);
            sendMsg(_controllerTextField.text, "192.168.100."+i.toString(), pt);
          }
          sendMsg(_controllerTextField.text, "192.168.100."+i.toString(), port);

        }


打开多个接受端口测试方便测试5个可以了
