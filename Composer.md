## 下载
<https://getcomposer.org/download/>

### 切换镜像源
- 全局：`composer config -g repo.packagist composer https://mirrors.aliyun.com/composer/`
- 项目：`composer config repo.packagist composer https://mirrors.aliyun.com/composer/`

### 取消配置
- 全局：composer config -g --unset repos.packagist
- 项目：composer config --unset repos.packagist

### 更新到最新版本
- composer self-update
- 2.4.2版本之后，管理员用户无法运行命令，需要执行：`export COMPOSER_ALLOW_SUPERUSER=1`


## 使用

### 初始化
- composer install，读取composer.lock文件为准
- composer update，读取composer.json文件为准

### 引入新包并实现版本约束
- composer require author/xxx:1.x
- composer require author/xxx:1.x@dev
- composer require author/xxx=1.x@alpha
- composer require author/xxx=1.x@beta
- composer require author/xxx:>=1.0
- composer require author/xxx:>=1.0 <2.0
- composer require author/xxx:>=1.0 <1.1 || >=1.2
- composer require author/xxx:1.0.* 相当于>=1.0 <1.1
- composer require author/xxx:^1.2.3 相当于>=1.2.3 <2.0.0
- 如果你想指定版本只要稳定版本，你可以在版本后面添加后缀-stable。
