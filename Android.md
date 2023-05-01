### build.gradle
- plugins
```
plugins {
    id 'com.android.application'
    id 'org.jetbrains.kotlin.android'
}
```
- android
```
android {
    compileSdk 32

    defaultConfig {
        applicationId "com.xuqingkai.myandroid"
        minSdk 23
        targetSdk 28
	multiDexEnabled true
        versionCode 1
        versionName "1.0"
        testInstrumentationRunner "androidx.test.runner.AndroidJUnitRunner"
    }

    buildTypes {
        release {
            minifyEnabled false
            proguardFiles getDefaultProguardFile('proguard-android-optimize.txt'), 'proguard-rules.pro'
        }
    }
    compileOptions {
        sourceCompatibility JavaVersion.VERSION_1_8
        targetCompatibility JavaVersion.VERSION_1_8
    }
    kotlinOptions {
        jvmTarget = '1.8'
    }
}
```

- dependencies
```
dependencies {

    implementation 'androidx.core:core-ktx:1.7.0'
    implementation 'androidx.appcompat:appcompat:1.3.0'
    implementation 'com.google.android.material:material:1.4.0'
    implementation 'androidx.constraintlayout:constraintlayout:2.0.4'
    //implementation 'com.squareup.okhttp3:okhttp:3.11.0'
    implementation 'com.squareup.retrofit2:retrofit:2.9.0'

}
```
- 安卓适配

### 将APP改为启动器
在AndroidManifest.xml文件中，找到默认activity行，加入以下两行
```
<category android:name="android.intent.category.HOME"/>  
<category android:name="android.intent.category.DEFAULT"/>
```

### 蓝牙startDiscovery()始终返回false
- 首先确认APP是否注册了位置权限：ACCESS_COARSE_LOCATION和ACCESS_FINE_LOCATION
- 判断设备是否开启了GPS位置开关
- 判断当前APP是否被授予了位置权限。
