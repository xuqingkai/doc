### 提示java版本不支持gradle版本

- The type java.lang.Object cannot be resolved It is indirectly referenced
项目（APP）右键，Open Module Settings，SDK Location，Gradle Settings，Gradle Projects，Gradle JDK，设置为1.8

### 修改包名
- 确认项目目录显示方案为Android，选中APP项目右侧的小齿轮的按钮，将下拉菜单中的Compact Middle Packages取消选中，防止包名各段都在一行显示。
- 找到APP项目，如：com.xuqingkai.myapp，想改哪段就在哪段上点右键，选择Refactor/Rename，在弹出的窗口中，选中In Whole Project
- 输入新的名称，点击Refactor按钮，在左下角的Refactoring Preview窗口中点击Do Refactor按钮，确认同步重命名其他模块的引用
- 打开APP项目的build.gradle文件，找到android节点下的defaultConfig节点下的applicationId，调整为完整的新包名，然后点击该窗口顶部的蓝色按钮Sync Now
- 完成。

### 去掉白色竖线
- setting，Editor，Code Style，（General），Hard wrap at，值从100改为0