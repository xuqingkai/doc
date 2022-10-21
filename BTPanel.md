### 1.安装原版脚本
首先必不可少的是原版的脚本 
```
wget -O install.sh http://f.cccyun.cc/bt/install_6.0.sh && bash install.sh
```

### 2.去除官网登陆绑定
重命名文件：/www/server/panel/data/bind.pl

### 3.破解插件
- 打开文件：/www/server/panel/data/plugin.json
- 全局替换`"endtime": -1`为`"endtime": 999999999999`

### 4.改图标
- 打开文件：/www/server/panel/data/plugin.json
- 搜索：is_user_status
- 把 "ltd": -1 和 "pro": -1 这两个 -1 改为 0
- ltd是企业版 pro是专业版
- -1代表没授权，0代表专业版永久授权

### 5.取消自动修复

- 解决方法1：在面板设置里打开离线模式。
- 解决方法2：/www/server/panel/data/plugin.json设为只读
- 命令行：chattr +i /www/server/panel/data/plugin.json
