Gwt   dev  env




Prj stuts

C:\0prj\paymentJava2024\src\main\java\com\example\MyGwtModule.gwt.xml

This file can put any postion..can tuto sacn find that

<?xml version="1.0" encoding="UTF-8"?>
<module  >

    <!--
     <source path="org/example"/>
     如果你的代码不在 client 包下，需要用 <source> 指令指定路径 -->

    <!-- Entry point -->
    <entry-point class="org.example.client.MyGwtApp" />

    <!-- Add more resources like images, CSS, etc -->
    <stylesheet src="style.css" />
    <inherits name="com.google.gwt.core.Core"/>
    <inherits name="com.google.gwt.core.Core"/>
    <inherits name="com.google.gwt.user.UI"/>
    <inherits name="com.google.gwt.user.UI"/>
    <inherits name="com.google.gwt.user.UI"/>
    <inherits name="com.google.gwt.user.UI"/>
</module>


C:\Users\attil\IdeaProjects\gwtPrj\src\main\java\org\example\client\MyGwtApp.java

Must in client pkg is bbetter..beir need def source param..


package org.example.client;

import com.google.gwt.core.client.EntryPoint;
import com.google.gwt.user.client.ui.RootPanel;
import com.google.gwt.user.client.ui.Button;
import com.google.gwt.user.client.ui.Label;

public class MyGwtApp implements EntryPoint {

    public static void main(String[] args) {
        System.out.println(888);
    }
    @Override
    public void onModuleLoad() {
        // 创建并显示一个简单的 UI 组件
        Label label = new Label("Hello, GWT!");
        Button button = new Button("Click Me");
        button.addClickHandler(event -> button.setText("Hello, GWT!"));
        // 将组件添加到根面板
        RootPanel.get().add(label);
        RootPanel.get().add(button);
    }
}



Complt  to js

Mvn complite  or   mvn gwt:complite

Then  gene   /target/
\target\gwtPrj-1.0-SNAPSHOT\org.example.MyGwtModule\org.example.MyGwtModule.nocache.js


MyGwtModule.html    impt    ...js
C:\Users\attil\IdeaProjects\gwtPrj\src\main\webapp\MyGwtModule.html
<!DOCTYPE html>
<html>
<head>
    <title>My GWT Application</title>
    <script type="text/javascript" language="javascript" src="org.example.MyGwtModule/org.example.MyGwtModule.nocache.js"></script>
</head>
<body>
<h1>Welcome to My GWT App!</h1>
</body>
</html>



