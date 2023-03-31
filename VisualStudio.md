# 使用技巧
## VisualStudio使用技巧
### VS2022打开项目提示：不支持 .NET Framework 4.0/4.5 项目解决办法
#### 4.0
- 打开网址：[4.0](https://www.nuget.org/packages/microsoft.netframework.referenceassemblies.net40) ，也可以直接下载[4.0](https://globalcdn.nuget.org/packages/microsoft.netframework.referenceassemblies.net40.1.0.2.nupkg)
- 点击右侧的：Download package，下载nupkg包，将文件后缀名改为.zip
- 解压里面的文件，复制“build\\.NETFramework\v4.0”目录里的所有文件到：C:\Program Files (x86)\Reference Assemblies\Microsoft\Framework\\.NETFramework\v4.0
#### 4.5
- 打开网址：[4.5](https://www.nuget.org/packages/microsoft.netframework.referenceassemblies.net45)，也可以直接下载[4.5](https://globalcdn.nuget.org/packages/microsoft.netframework.referenceassemblies.net45.1.0.2.nupkg)
- 点击右侧的：Download package，下载nupkg包，将文件后缀名改为.zip
- 解压里面的文件，复制“build\\.NETFramework\v4.5”目录里的所有文件到：C:\Program Files (x86)\Reference Assemblies\Microsoft\Framework\\.NETFramework\v4.5
#### 4.6
- 打开网址：[4.6](https://www.nuget.org/packages/microsoft.netframework.referenceassemblies.net46)，也可以直接下载[4.6](https://globalcdn.nuget.org/packages/microsoft.netframework.referenceassemblies.net46.1.0.2.nupkg)
- 点击右侧的：Download package，下载nupkg包，将文件后缀名改为.zip
- 解压里面的文件，复制“build\\.NETFramework\v4.6”目录里的所有文件到：C:\Program Files (x86)\Reference Assemblies\Microsoft\Framework\\.NETFramework\v4.6


### win11下vs不支持.NET Framework 4.0，
- 运行vs installer，单个组件，把所有的Framework都选上
