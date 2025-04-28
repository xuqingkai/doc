### 重新注册IIS里的ASP.NET
- 开始-运行：C:\Windows\Microsoft.NET\Framework\v4.0.30319\aspnet_regiis.exe -i

### win10安装iis无法安装Framework3.5
- 我的电脑→管理→服务和应用程序→服务→windows Update→属性→手动→启动
- gpedit.msc→计算机配置→管理模板→系统→指定可选组件安装和组件修复的设备→点选已启用。
- 再选中“直接与 Windows Update 联系以下载修复内容而非使用 Windows Server Update Services (WSUS)”复选框

### window server 2012r2 无法安装Framework3.5
- 安装一个或多个角色、角色服务或功能失败。
- 找不到源文件。请再次尝试在新的”添加角色和功能“向导会话中安装角色、角色服务或功能，然后在向导的”确认”页中单击“指定备用源路径”以指定安装所需的源文件的有效位置。目标服务器的计算机帐户必须能够访问该位置。
- 卸载更新补丁：kb5027141，kb5028872，kb5028970，kb5029915

### Windows每个版本自带的.NET版本，与支持的最高.NET版本
| Windows版本 | 自带.NET Framework 版本 | 支持最高的 .NET Framework 版本 |
|  ----  | ----  | ---- |
| Windows NT 4.0 SP6a、2000 |  | .NET Framework 1.1 SP1 |
| Windows 98, 98SE, Me, 2000 SP3 |  | .NET Framework 2.0 |
| Windows 2000 SP4 |  | .NET Framework 2.0 SP2 |
| Windows XP SP1 | .NET Framework 1.0 SP2 | .NET Framework 1.0 SP2 |
| Windows XP SP2 | .NET Framework 1.1 SP1 | .NET Framework 3.5 SP1 |
| Windows XP SP3 | .NET Framework 1.1 SP1 | .NET Framework 4.0 |
| Windows Vista | .NET Framework 3.0 | .NET Framework 3.5 SP1 |
| Windows Vista SP1	| .NET Framework 3.0 SP1 | .NET Framework 4.0 |
| Windows Vista SP2	| .NET Framework 3.0 SP2 | .NET Framework 4.6 |
| Windows 7	| .NET Framework 3.5.1 SP1 | .NET Framework 4.0 |
| Windows 7 SP1	| .NET Framework 3.5.1 SP1 | Latest |
| Windows 8	| .NET Framework 3.5.1 SP1 + 4.5 | .NET Framework 4.6.2 |
| Windows 8.1	| .NET Framework 3.5.1 SP1 + 4.5.1 | .NET Framework 4.5.2 |
| Windows 8.1 Update | .NET Framework 3.5.1 SP1 + 4.5 | Latest |
| Windows 10 （1507） | .NET Framework 4.6 | Latest |
| Windows 10 （1511） | .NET Framework 4.6.1 | Latest |
| Windows 10 （1607） | .NET Framework 4.6.2 | Latest |
| Windows 10 （1703） | .NET Framework 4.7 | Latest |
| Windows 10 （1709） | .NET Framework 4.7.1 | Latest |
| Windows 10 （1803 ~ 1809） | .NET Framework 4.7.2 | Latest |
| Windows 10 （1903 ~ v20H2） | .NET Framework 4.8 | Latest |
| Windows 11 | .NET Framework 4.8 | Latest（？） |
