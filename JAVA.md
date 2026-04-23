### 下载地址
- https://www.oracle.com/java/technologies/downloads/archive/
- https://repo.huaweicloud.com/java/jdk/
- http://www.codebaoku.com/jdk/jdk-index.html


### 环境变量
WIN10：设置，关于，高级系统设置

### 系统变量
- JAVA_HOME【新建】
```
D:\Program Files\Java\jdk1.8.0_202
```

- CLASSPATH【新建】
```
;%JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib\tools.jar;
```

- PATH【追加】,从 JDK 9 开始，\jre\bin也不需要了
```
%JAVA_HOME%\bin
%JAVA_HOME%\jre\bin
```
### 运行JAR包
java -jar your-application.jar
