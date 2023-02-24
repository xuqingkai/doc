### 安装
- 【LINUX】
```
composer create-project topthink/think wwwroot
```
### 更新
```
composer update topthink/framework
```

###

### 常见问题修复
- 报错：Driver [Think] not supported，原因：忘记引入视图模块
```
composer require topthink/think-view
```
- 控制器不存在:app\controller\Index，原因：没有装多应用模式扩展
```
composer require topthink/think-multi-app
```
