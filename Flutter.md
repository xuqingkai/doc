## VSCode

### Dart SDK
https://dart.dev/get-dart/archive
- 2.12开始，默认空值安全保护模式，及null safety模式，定义变量需要用String 或者String?区分
- 插件市场：https://dart.dev/packages

### Flutter SDK下载地址，自带了Dart SDK
英文官网：https://docs.flutter.dev/development/tools/sdk/releases  
中文官网：https://flutter.cn/docs/development/tools/sdk/releases

### 环境变量
- Path
```
指向Flutter SDK目录下的bin目录
```
### 依赖配置文件：pubspec.yaml
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

### 相关命令
- 初始化依赖：pub get或者flutter pub get


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
    //https://maven.google.com/
    if (!platform.environment.containsKey(kEnvCloudUrl))
      'https://dl.google.com/dl/android/maven2/',
  ];
}
```

### 需要安装的插件
- Code Runner，右键运行代码工具
- Dart，开发语言
- Flutter，框架
- Flutter Widget Snippets，调试用的，可不装

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
flutter create myFirstFlutterProject

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
### 相关名录
- 检查环境：flutter doctor
- 运行项目：flutter run
### 错误处理
- 如果提示Android licenses no accept，可以运行flutter run --android-licenses
- 如果提示：Command-line错误，可以尝试从Android Studio，Tools，SDK Manager，SDK Tools中安装

