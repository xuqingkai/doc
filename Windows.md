### 修复win11无音量控制条
- 原因：使用DISM++隐藏操作中心任务栏图标导致，可尝试恢复，如不行则往下
- 开始运行，输入powersheell，再输入
```
Get-AppxPackage | % { Add-AppxPackage -DisableDevelopmentMode -Register "$($_.InstallLocation)\AppxManifest.xml" -verbose }
```
### 查看端口情况
- netstat -ano

### windows照片查看器无法显示此图片
- 开始，控制面板，查看方式选大图标，颜色管理，高级，（Windows颜色系统），（设备配置文件），选“Agfa：Swop Standard”。

### WIN2012R2多用户同时远程
运行,输入"gpedit.msc"命令 
计算机组策略→ 计算机配置 → 管理模板 → windows组件 → 远程桌面服务 → 远程桌面会话主机 → 连接 
在“连接”界面中 
1，双击打开“将远程桌面服务用户限制到单独的远程桌面服务会话”，选择“已禁用”，确定 
2，双击打开“限制连接的数量”，选择“已启用”，然后把选项里面“允许的RD最大连接数”改为5，确定 

### WIN2012 显示桌面
rundll32.exe shell32.dll,Control_RunDLL desk.cpl,,0 

### 更改默认安装目录
开始，运行，regedit 
[HKEY＿LOCAL＿MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion]  → ProgramFilesDir 
双击输入：ProgramFiles 

### 安装windows11系统时，跳过创建联网账号，只创建本地账户
安装 Windows 11 时，使用用户名 no@thankyou.com 登录，即可跳过联网账户，轻松创建本地账 
