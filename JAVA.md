### 下载地址
- https://www.oracle.com/java/technologies/downloads/archive/
- https://repo.huaweicloud.com/java/jdk/
- http://www.codebaoku.com/jdk/jdk-index.html
- https://developers.redhat.com/products/openjdk/download
```
JDK和Open JDK都是Java开发工具包的软件和规范。从本质上讲，Oracle JDK和Open JDK之间在代码上几乎没有变化，因此它们在功能上非常相似，在常规使用上几乎没有区别。
Open JDK和Oracle JDK之间最大的区别在于，Open JDK是由Oracle、Red Hat和社区维护的开源项目，使用的是GPLv2 with Classpath Exception许可证，对于商业用途开放，可以免费使用。而Oracle JDK是闭源的，由Oracle维护，使用的是‌Oracle Binary Code License，对于商业用途存在一定的限制，而且需要付费。
```

### 环境变量
WIN10：设置，关于，高级系统设置

### 系统变量
- JAVA_HOME
```
D:\Program Files\Java\jdk1.8.0_202
```

- CLASSPATH
```
;%JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib\tools.jar;
```

- PATH
```
%JAVA_HOME%\bin
%JAVA_HOME%\jre\bin
```
### 运行JAR包
java -jar your-application.jar
