​​1.安装原版脚本
首先必不可少的是原版的脚本 
wget -O install.sh http://f.cccyun.cc/bt/install_6.0.sh && bash install.sh

2.去除官网登陆绑定
他让你绑定你就绑定？？no no no

这是破解的核心一旦绑定破坏就达不到目的了

这里提供了两次方法直接在终端执行就行了

 
删除文件

#删除登录文件命令

cd

mv /www/server/panel/data/bind.pl ./

重命名文件为binl.pl.bak (推荐)

#重命名此文件为bind.pl.bak

cd

mv /www/server/panel/data/bind.pl /www/server/panel/data/bind.pl.bak

执行成功后不会有任何提示 这时候我们刷新宝塔就不会让我们绑定啦！

3.破解插件
我进进到 /www/server/panel/data/ 目录

编辑plugin.json文件

点击替换按钮，搜索

“endtime”: -1

替换为

“endtime”: 999999999999

点击 All进行全部替换

https://r.sinaimg.cn/large/article/b85b1944b3e97f7eb083fcfcc455ca89
然后软件都可以使用了

https://r.sinaimg.cn/large/article/b0367deb640828199308280ed916459a
4.改图标
图标还是在那个文件

搜索

is_user_status

把 “ltd”: -1 和 “pro”: -1 这两个 -1 改为 0

ltd是企业版 pro是专业版

-1代表没授权，0代表专业版永久授权

然后点击保存按钮即可

5.取消自动修复
因为宝塔会自动修复

解决方法1

在面板设置里打开离线模式。

解决方法2

用Linux chattr命令改变文件属性。

打开宝塔终端，输入下面代码：

chattr +i /www/server/panel/data/plugin.json

https://r.sinaimg.cn/large/article/8c6093520bf29c2c870395c0d9c6826e
解除输入

chattr -i /www/server/panel/data/plugin.json​​​​
