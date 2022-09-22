## 本地版本

## 官方web版本
<https://code.visualstudio.com/docs/remote/vscode-server>

## Web版
### 安装
- https://github.com/coder/code-server/releases
- CentOS选择tar.gz版本，注意amd和arm架构
- 选择合适的版本：也可以直接下载下来再通过宝塔上传到服务器
```
wget https://github.com/coder/code-server/releases/download/v4.5.0/code-server-4.5.0-linux-amd64.tar.gz
```
- 解压：也可直接在宝塔里解压
```
tar xf code-server-4.5.0-linux-amd64.tar.gz
```
- 进入解压后的目录：也可以宝塔里直接点进去
```
cd code-server-4.5.0-linux-amd64
```
- 先运行根目录的code-server命令，生成配置文件，该命令只会只能运行一次，之后失效
```
./code-server
```
- 数据目录：/root/.local/share/code-server，root指的是当前操作系统用的账户名
- 打开配置文件：/root/.config/code-server/config.yaml，root指的是当前操作系统用的账户名
```
bind-addr: 0.0.0.0:8080
auth: password
password: 1234567890
cert: false
```
- 重新运行启动命令：注意和上面那个一次性命令的区别
```
./bin/code-server
```
- 运行结果
```
[2022-07-14T06:43:17.709Z] info  code-server 4.5.0 02b9d7ee856e31d9008d1ff24a175ff03b49010e
[2022-07-14T06:43:17.710Z] info  Using user-data-dir ~/.local/share/code-server
[2022-07-14T06:43:17.724Z] info  Using config file ~/.config/code-server/config.yaml
[2022-07-14T06:43:17.724Z] info  HTTP server listening on http://0.0.0.0:8080/ 
[2022-07-14T06:43:17.725Z] info    - Authentication is enabled
[2022-07-14T06:43:17.725Z] info      - Using password from ~/.config/code-server/config.yaml
[2022-07-14T06:43:17.725Z] info    - Not serving HTTPS 
```
- 后台运行（不要直接关闭窗口，要用exit退出）
```
nohup ./bin/code-server &
【Ctrl+C】
exit
```
- 预览地址
```
http://服务器IP或者域名:8080/
```
- 禁用自动保存，刚装完默认是自动保存模式的，保存无提示，很不方便
- 打开setting，搜索【auto save】，一共三处都关闭：【Files: Auto Save】【Files: Auto Save Delay】【Files › Refactoring: Auto Save】
