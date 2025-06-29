Smpl arch jar lib






Wb api
Spark java 


其他轻量级选择
如果你想要更轻量的框架，可以考虑：
Javalin：简单易用，适合快速构建小型API。
Spark Java：非常简洁的API设计，适合小项目。
总结
对于大多数项目，Spring Boot是最推荐的选择，因为它的功能强大且易于使用。对于更小的项目或快速原型开发，可以考虑Javalin或Spark Java。
Javalin需要指定版本不知道，使用sparkjava

注意版本匹配，使用版本spark2.9.4，搭配的jetty9。不知为什么不能pom，只能手动jar加载

<dependency>
    <groupId>aaaa</groupId>
    <artifactId>bbbb</artifactId>
    <version>3.1.0</version>
    <scope>system</scope>
    <systemPath>${project.basedir}/jars/jetty-server-9.4.43.v20210629.jar</systemPath>



</dependency>

<dependency>
    <groupId>aaaa</groupId>
    <artifactId>bbbb</artifactId>
    <version>3.1.0</version>
    <scope>system</scope>
    <systemPath>${project.basedir}/jars/jetty-http-9.4.43.v20210629.jarr</systemPath>



</dependency>


<dependency>
    <groupId>aaaa</groupId>
    <artifactId>bbbb</artifactId>
    <version>3.1.0</version>
    <scope>system</scope>
    <systemPath>${project.basedir}/jars/javax.servlet-api-3.1.0.jar</systemPath>



</dependency>



Spirng trble

Store
Spring jdbc
Mybatis trble

Store 全面nosql话
Sqlt kv 模式存储即可 没有合适的kv本地库

