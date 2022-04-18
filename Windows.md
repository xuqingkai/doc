### 修复win11无音量控制条
- 原因：使用DISM++隐藏操作中心任务栏图标导致，可尝试恢复，如不行则往下
- 开始运行，输入powersheell，再输入
```
Get-AppxPackage | % { Add-AppxPackage -DisableDevelopmentMode -Register "$($_.InstallLocation)\AppxManifest.xml" -verbose }
```
