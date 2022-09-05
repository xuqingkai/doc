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
