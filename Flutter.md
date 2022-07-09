## VSCode

### Flutter SDK下载地址，自带了Dart SDK
https://docs.flutter.dev/development/tools/sdk/releases

### 需要安装的插件
- Dart，开发语言
- Flutter，框架
- Flutter Widget Snippets，调试用的，可不装

### 创建项目命令
flutter create myFirstFlutterProject

### 更改镜像地址
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
