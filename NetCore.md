### 常用命令
- 创建项目前，查看可用项目模板的列表
```
dotnet new list
```

- 创建新的.Net项目或者文件
```
dotnet new [template]
```

- 构建.Net项目，并编译二进制文件
```
dotnet build 
```

- 构建并运行.Net项目
```
dotnet run
```

- 还原.Net项目中引用的依赖项
```
dotnet restore
```

- 将一个或者多个项目添加到解决方案，多个项目路径用空格隔开
```
dotnet sln add {project path}
```

- 列出解决方案文件中的所有项目
```
dotnet sln list
```

- 从解决方案中移除一个或者多个项目，多个项目路径用空格隔开
```
dotnet sln remove {project path}
```

- 将包添加到项目中
```
dotnet add package Microsoft.AspNetCore.xxx
```

- 将引用添加到当前项目中
```
dotnet add reference src/xxxx.csproj
```

- 将项目ProjectA添加对ProjectB的引用
```
dotnet add src/ProjectA.csproj reference src/ProjectB.csproj
```

- 清理.Net项目的构建
```
dotnet clean
```
