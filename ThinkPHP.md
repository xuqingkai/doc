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

- 如果你使用ThinkPHP 6.1+版本，并且需要使用think-filesystem上传扩展
```
composer require topthink/think-filesystem
```

### PlanetScale数据库在thinkphp的证书配置模式
```
'mysql' => [
            // 数据库类型
            'type'            => env('database.type', 'mysql'),
            // 服务器地址
            'hostname'        => env('database.hostname', 'aws.connect.psdb.cloud'),//
            // 数据库名
            'database'        => env('database.database', ''),
            // 用户名
            'username'        => env('database.username', ''),
            // 密码
            'password'        => env('database.password', ''),
            // 端口
            'hostport'        => env('database.hostport', '3306'),
            // 数据库连接参数
            'params'          => [
                //Debian/Ubuntu
                //\PDO::MYSQL_ATTR_SSL_CA => "/etc/ssl/certs/ca-certificates.crt",
                //RedHat/Fedora/CentOS
                \PDO::MYSQL_ATTR_SSL_CA => "/etc/pki/tls/certs/ca-bundle.crt",
            ],
```
