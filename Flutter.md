## VSCode

### Flutter SDK下载地址，自带了Dart SDK
https://docs.flutter.dev/development/tools/sdk/releases


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
- Dart，开发语言
- Flutter，框架
- Flutter Widget Snippets，调试用的，可不装

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
