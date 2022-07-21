## VSCode

### Dart:
- https://dart.cn
- https://github.com/dart-lang/sdk
#### 特殊说明
- 2.12开始，默认空值安全保护模式，及null safety模式，定义变量需要用String 或者String?区分

### SDK
- https://dart.dev/get-dart/archive  
- https://dart.cn/tools/sdk/archive

### packages
- https://dart.dev/packages

### Flutter 
- https://flutter.cn
- https://github.com/flutter/flutter
### SDK：已经包含了Dart SDK，所以上面的内容其实不用下载
- https://docs.flutter.dev/development/tools/sdk/releases  
- https://flutter.cn/docs/development/tools/sdk/releases

### 环境变量
- Path
```
指向Flutter SDK目录下的bin目录
```
### JAVA SDK
- http://www.codebaoku.com/jdk/jdk-index.html
- JAVA_HOME
```
D:\Program Files\Java\jdk1.8.0_202
```

- CLASSPATH
```
.;%JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib\tools.jar
```

- PATH
```
%JAVA_HOME%\bin
%JAVA_HOME%\jre\bin
```

### 更改SDK镜像地址
- ./Flutter_SDK/packages/flutter_tools/gradle/flutter.gradle
```
buildscript {
    repositories {
        //google()
        //mavenCentral()
        maven { url 'https://maven.aliyun.com/repository/google' }
        maven { url 'https://maven.aliyun.com/repository/jcenter' }
        maven { url 'https://maven.aliyun.com/repository/public' }
    }
    dependencies {
        /* When bumping, also update ndkVersion above. */
        classpath 'com.android.tools.build:gradle:4.1.0'
    }
}
```
```
class FlutterPlugin implements Plugin<Project> {
    //private static final String DEFAULT_MAVEN_HOST = "https://storage.googleapis.com";
    private static final String DEFAULT_MAVEN_HOST = "https://storage.flutter-io.cn";
```

### 更改引入地址
- ./Flutter_SDK/packages/flutter_tools/lib/src/http_host_validator.dart
```
/// Android specific required HTTP hosts.
List<String> androidRequiredHttpHosts(Platform platform) {
  return <String>[
    // If kEnvCloudUrl is set, it will be used as the maven host
    if (!platform.environment.containsKey(kEnvCloudUrl))
      //'https://maven.google.com/',
      'https://dl.google.com/dl/android/maven2/',
  ];
}
```

### 需要安装的插件
- Code Runner，右键运行代码工具
- Dart，开发语言
- Flutter，框架
- Awesome Widget Snippets，代码自动化，构建对象基本结构时用，简单几个字母，基本结构就自动输入好了

### 设定Android SDK环境变量
- ANDROID_HOME
```
指向Android SDK目录下的bin目录
```

- FLUTTER_STORAGE_BASE_URL
```
https://storage.flutter-io.cn/
https://mirrors.tuna.tsinghua.edu.cn/flutter
```

- PUB_HOSTED_URL 
```
https://pub.flutter-io.cn/
https://mirrors.tuna.tsinghua.edu.cn/dart-pub
```

- CHROME_EXECUTABLE，指向谷歌浏览器
```
C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe
```


### 创建项目命令
```
flutter create myFirstFlutterProject
```

### 依赖文件（pubspec.yaml）格式及注意事项：
```
name: test
description: none
version: 1.0.0
environment:
  sdk: '^2.17.5'
dependencies: 
  http: ^0.13.0
```
- 冒号后面必须紧跟一个空格

### 初始化依赖
- 命令：pub get或者flutter pub get

### 更改项目的镜像地址
- ./android/build.gradle
```
buildscript {
    ext.kotlin_version = '1.6.10'
    repositories {
        //google()
        //mavenCentral()
        maven { url 'https://maven.aliyun.com/repository/google' }
        maven { url 'https://maven.aliyun.com/repository/jcenter' }
    }
}
allprojects {
    repositories {
        //google()
        //mavenCentral()
        maven { url 'https://maven.aliyun.com/repository/google' }
        maven { url 'https://maven.aliyun.com/repository/jcenter' }
    }
}
```
### 检查环境：flutter doctor

#### Android licenses no accept
```
flutter run --android-licenses
```
#### cmdline-tools component is missing

- 可以尝试从Android Studio，Tools，SDK Manager，SDK Tools中安装Android SDK Command-line Tools (latest)
- 命令行,powershell如不行，则必须从运行cmd进入终端
```
cd D:\android\sdk\
.\sdkmanager --sdk_root=D:\Android\Sdk\ "cmdline-tools;latest"
.\sdkmanager --sdk_root=%ANDROID_HOME% "cmdline-tools;latest"
```
###  运行项目：flutter run
- 如果卡在下面一行一直运行
```
Running Gradle task 'assembleDebug'...                 /
```
- 1，忘记更改了项目的镜像地址，切记是两处
- 2，设备的安卓版本是Android SDK里没有了，正在拼命下载中，，，等待即可
### 编译库或者模块：
```
flutter create -t module my_flutter_library
```

### VSCode 编辑dart文件时，中间有条白色竖线，这是为了给右侧流出模拟器空间的，禁用方式：
- 打开文件：`C:\Users\Administrator\AppData\Roaming\Code\User\settings.json`
- 修改[dart]，editor.rulers，为空数组即可，如下：
```
{
    "security.workspace.trust.untrustedFiles": "open",
    "security.workspace.trust.enabled": false,
    "[dart]": {
        "editor.formatOnSave": true,
        "editor.formatOnType": true,
        "editor.rulers": [],
        "editor.selectionHighlight": false,
        "editor.suggest.snippetsPreventQuickSuggestions": false,
        "editor.suggestSelection": "first",
        "editor.tabCompletion": "onlySnippets",
        "editor.wordBasedSuggestions": false
    }
}
```

