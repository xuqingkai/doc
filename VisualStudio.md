# 使用技巧
## VisualStudio使用技巧
### VS2022打开项目提示：不支持 .NET Framework 4.0/4.5/4.5.1/4.5.2/4.6/4.6.1/4.6.2.. 项目解决办法
- 打开网址：[4.0](https://www.nuget.org/packages/microsoft.netframework.referenceassemblies.net40)、[4.5](https://www.nuget.org/packages/microsoft.netframework.referenceassemblies.net45)、[4.5.1](https://www.nuget.org/packages/microsoft.netframework.referenceassemblies.net451)、[4.5.2](https://www.nuget.org/packages/microsoft.netframework.referenceassemblies.net452)、[4.6](https://www.nuget.org/packages/microsoft.netframework.referenceassemblies.net46)、[4.6.1](https://www.nuget.org/packages/microsoft.netframework.referenceassemblies.net461)、[4.6.2](https://www.nuget.org/packages/microsoft.netframework.referenceassemblies.net462)、[4.7](https://www.nuget.org/packages/microsoft.netframework.referenceassemblies.net47)
- 点击右侧的：Download package，下载nupkg包，将文件后缀名改为.zip
- 解压里面的文件，复制“build\\.NETFramework\v4.X”目录里的所有文件到：C:\Program Files (x86)\Reference Assemblies\Microsoft\Framework\\.NETFramework\v4.X
- 文件


### win11下vs不支持.NET Framework 4.0，
- 运行vs installer，单个组件，把所有的Framework都选上
