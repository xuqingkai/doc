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
- composer require author/xxx:1.3.2
- composer require author/xxx=1.3.2，同上一条
- composer require author/xxx:1.3.*
- composer require author/xxx:~1.3.2，等同于>=1.3.2且<1.4.0，本质上同上一条，尾版本号可以不同
- composer require author/xxx:1.*
- composer require author/xxx:^1.3.2，等同于>=1.3.2且<2.0.0，本质上同上一条，首版本号必须相同
- composer require author/xxx:>=1.3.2，只要不低于1.3.2，甚至4.3.2也可以，所以很宽泛
- composer require author/xxx:<=1.3.2，必须不高于1.3.2，适应于高版本出现了不兼容旧版本的某功能的情况
- composer require author/xxx:1.1@dev
- composer require author/xxx:1.3@alpha
- composer require author/xxx:1.3@beta
- 如果你想指定版本只要稳定版本，你可以在版本后面添加后缀-stable。
