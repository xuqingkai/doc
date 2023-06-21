## 修改gradle的缓存目录
### 全局
菜单File，Setting，Build...，gradle
### 单个项目
修改gradle.properties文件，gradle.user.home=D:/Cache/.gradle


## 提示java版本不支持gradle版本

- The type java.lang.Object cannot be resolved It is indirectly referenced
- 项目（APP）右键，Open Module Settings，SDK Location，Gradle Settings，Gradle Projects，Gradle JDK，设置为1.8

## 修改包名
- 确认项目目录显示方案为Android，选中APP项目右侧的小齿轮的按钮，将下拉菜单中的Compact Middle Packages取消选中，防止包名各段都在一行显示。
- 找到APP项目，如：com.xuqingkai.myapp，想改哪段就在哪段上点右键，选择Refactor/Rename，在弹出的窗口中，选中In Whole Project
- 输入新的名称，点击Refactor按钮，在左下角的Refactoring Preview窗口中点击Do Refactor按钮，确认同步重命名其他模块的引用
- 打开APP项目的build.gradle文件，找到android节点下的defaultConfig节点下的applicationId，调整为完整的新包名，然后点击该窗口顶部的蓝色按钮Sync Now
- 完成。

## 去掉白色竖线
- setting，Editor，Code Style，（General），Hard wrap at，值从100改为0

## 报错：NDK at D:\android\sdk\ndk-bundle did not have a source.properties file
- IDE顶部菜单File，Project Structure，SDK Location，倒数第一行的蓝色链接Download Android NDK

## Android Gradle Plugin版本与Gradle版本、JDK版本对应关系，必须一一对应
- 打开项目，先确定Gradle版本，再确定AGP与JDK版本
- 查看Gradle版本1：gradle\wrapper\gradle-wrapper.propertie
- 查看Gradle版本2：IDE顶部菜单File，Project Structure，Project，Gradle Version
- AGP版本设置：IDE顶部菜单File，Project Structure，Project，Android Gradle Plugin Version
- JDK版本设置：IDE顶部菜单File，Project Structure，SDK Location，最后一行的蓝色链接Gradle Settings，最后一行Gradle JDK

|  AGP Version | Gradle Version | JDK Version
|  ----  | ----  | ----  |
| 1.0.0 - 1.1.3 | 2.2.1 - 2.3 | 1.8/8 |
| 1.2.0 - 1.3.1 | 2.2.1 - 2.9 | 1.8/8 |
| 1.5.0 | 2.2.1 - 2.13 | 1.8/8 |
| 2.0.0 - 2.1.2 | 2.10 - 2.13 | 1.8/8 |
| 2.1.3 - 2.2.3 | 2.14.1 - 3.5 | 1.8/8 |
| 2.3.0+ | 3.3+ | 1.8/8 |
| 3.0.0+ | 4.1+ | 1.8/8 |
| 3.1.0+ | 4.4+ | 1.8/8 |
| 3.2.0 - 3.2.1 | 4.6+ | 1.8/8 |
| 3.3.0 - 3.3.3 | 4.10.1+ | 1.8/8 |
| 3.4.0 - 3.4.3 | 5.1.1+ | 1.8/8 |
| 3.5.0 - 3.5.4 | 5.4.1+ | 1.8/8 |
| 3.6.0 - 3.6.4 | 5.6.4+ | 1.8/8 |
| 4.0.0+ | 6.1.1+ | 1.8/8 |
| 4.1.0+ | 6.5+ | 1.8/8 |
| 4.2.0+ | 6.7.1+ | 1.8/8 |
| 7.0 | 7.0+ | 11 |
| 7.1 | 7.2+ | 11 |
| 7.2 | 7.3.3+ | 11 |
