### 请务必打开fileinfo扩展，否则composer不好用
### 安装
- 【LINUX】
```
composer create-project topthink/think wwwroot
```
### 更新
```
composer update topthink/framework
```

### thinkphp5更改入口文件从public到根目录（解决public/index.php访问）
- 将public里的index.php和.htaccess文件移动到根目录
- 更改index.php里引用核心文件的那行，路径改为根目录即可
- 注意不要用hello测试地址，因为路由有专门设置，结果会出现意外错误
### 常见问题修复
- 报错：Driver [Think] not supported，原因：忘记引入视图模块
```
composer require topthink/think-view
```
- 控制器不存在:app\controller\Index，原因：没有装多应用模式扩展
```
composer require topthink/think-multi-app
```


