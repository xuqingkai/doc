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
- 更改第16行为：`require __DIR__ . '/./thinkphp/base.php';`
### 常见问题修复
- 报错：Driver [Think] not supported，原因：忘记引入视图模块
```
composer require topthink/think-view
```
- 控制器不存在:app\controller\Index，原因：没有装多应用模式扩展
```
composer require topthink/think-multi-app
```


