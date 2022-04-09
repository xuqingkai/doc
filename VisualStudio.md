# VisualStudio使用技巧

## VS2022打开项目提示：不支持 .NET Framework 4.5 项目解决办法
- 打开网址：https://www.nuget.org/packages/microsoft.netframework.referenceassemblies.net45
- 点击右侧的：Download package  (18.9 MB)，下载nupkg包，将文件后缀名改为.zip
- 解压里面的文件，复制“build\.NETFramework\v4.5”目录里的所有文件到：C:\Program Files (x86)\Reference Assemblies\Microsoft\Framework\.NETFramework\v4.5
