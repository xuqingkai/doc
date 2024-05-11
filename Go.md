### 官网
- 网址：https://golang.google.cn/

### 环境变量
- PATH：`D:\GoSDK\1.18.4\bin`
- GOROOT：`D:\GoSDK\1.18.4`
- GOPROXY：`https://goproxy.cn,redirect`（redirect：能走代理就走代理，否则去找github）

### 解决运行go install命令无反应的情况：https://goproxy.cn
Go 1.13 及以上（推荐），打开你的终端并执行
```
go env -w GO111MODULE=on
go env -w GOPROXY=https://goproxy.cn,direct
```
### beego框架开发命令bee安装
- 下载https://github.com/beego/bee/releases压缩包，并解压到新文件夹
- 在该文件夹下，运行go build，会在当前文件夹下生成bee.exe
- 复制bee.exe到C:\Users\Administrator\go\bin
- 注意该路径是否已经添加到系统变量
