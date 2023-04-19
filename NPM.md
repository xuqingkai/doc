## 常用

- 更改全局目录，记得先创建好npm_global目录
npm config set prefix "D:\Program Files\nodejs\npm_global"

- 更改缓存目录，记得先创建好npm-cache目录
npm config set cache "D:\Program Files\nodejs\npm-cache"

- 本地运行
npm run dev

- 生成测试包
npm run build:stage

- 生成生产包
npm run build:prod

## 其他

- 查看 npm 版本
npm -v：

- 初始化：一步步生成项目配置文件package.json，
npm init

3. npm install：会根据项目中的 package.json 文件自动给下载项目中所需的全部依赖

4. npm insall 包名 --save-dev (npm install 包名 -D) : 安装的包只用于开发环境，不用于生产环境，会出现在 package.json 文件中的 devDependenceies 属性中

5. npm insall 包名 --save (npm install 包名 -S) :  安装的包需要发布到生产环境的，会出现在 package.json 文件中的 dependenceies 属性中

6. npm list：查看当前目录下已安装的node包

7. npm list -g：查看全局已经安装过的node包

8. npm --help : 查看npm帮助命令

9. npm update 包名 : 更新指定包

10. npm uninstall 包名 : 卸载指定包

11. npm config list  :查看配置信息

12. npm 指定命令--help : 查看指定命令的帮助

13. npm info 指定包名 : 查看远程npm上指定包的所有版本信息

14. npm install -g cnpm --registry=https://registry.npmmirror.com : 修改包下载源，此例修改为了淘宝镜像

15. npm root ：查看当前包的安装路径

16. npm root -g : 查看全局的包的安装路径

17. npm ls 包名 : 查看本地安装的指定包及版本信息，没有显示empty

18. npm ls包名 -g : 查看全局安装的指定包及版本信息，没有显示empty
