## 常用

#### 查看 npm 版本
npm -v：

#### 初始化项目：一步步生成项目配置文件package.json，
npm init

#### 下载依赖：根据package.json下载所需依赖到./node_modules
npm install

#### 安装依赖到项目目录，无任何环境清单备案，即后续项目初始依赖时就没了
- npm insall 包名

#### 安装依赖到项目目录，并备案到到生产环境依赖清单，测试更不用说了
- npm insall 包名 --save 或者 npm insall 包名 -S

#### 安装依赖到项目目录，并只备案到开发环境依赖清单，生产环境无
- npm insall 包名 --save-dev 或者 npm insall 包名 -D

#### 安装依赖全局目录
- npm insall 包名 --g

#### 更新指定包
npm update 包名

#### 修改包源
npm install -g cnpm --registry=https://registry.npmmirror.com

#### 更改全局目录，记得先创建好npm_global目录
npm config set prefix "D:\Program Files\nodejs\npm_global"

#### 更改缓存目录，记得先创建好npm-cache目录
npm config set cache "D:\Program Files\nodejs\npm-cache"

#### 本地运行
npm run dev

#### 生成测试包
npm run build:stage

#### 生成生产包
npm run build:prod





## 其他

#### 帮助
npm --help

#### 查看指定命令的帮助
npm 命令名 --help

#### 查看当前项目已安装的依赖包
npm list

#### 查看全局已安装的依赖包
npm list -g

#### 拉取指定包的所有版本信息
npm info 包名

#### 查看本地安装的指定包及版本信息
npm ls 包名 

#### 查看全局安装的指定包及版本信息
npm ls 包名 -g

#### 卸载指定包
npm uninstall 包名

#### 查看配置信息
npm config list

#### 查看当前包的安装路径
npm root 

#### 查看全局的包的安装路径
npm root -g
