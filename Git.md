# 文档

## 阿里云git使用建议
https://thoughts.teambition.com/sharespace/5d88b152037db60015203fd3/folders/5ff6db40aae9e200468c5fbc

## 【使用规范】
- master分支一般为主分支，默认分支，是作为软件最新的版本发布线。
- develop分支是主力开发分支，各小组分支开发完毕并检验后合并到此，测试人员随时可以从此拉取代码打包测试。
- master-x.x.x，软件的正式版本发布后的分支或者发现bug的修复线，有的公司修复完毕后会删除该类分支
- develop-x.x.x 平时开发时，每个小组或者个人需要单拉分支，在自己的分支线上开发，完毕后再去合并。


## 【使用技巧】

### Linux初始化配置
- 1，建议先下载并更新到最新版本：参考下面一条
- 2，设置自动保存密码：git config --global credential.helper store
- 3，设置支持中文编码：`git config --global core.quotepath false`
- 4，设置全局账号：`git config --global user.name xuqingkai`
- 5，设置全局邮箱：`git config --global user.email xuqingkai@git.com`
- 6，克隆仓库：`git clone https://github.com/xuqingkai/test.git test`
- 7，提示输入用户名和密码，密码也就是token，需要从https://github.com/settings/tokens获取，经典模式即可
- 8，无法使用云IDE的Git，是可能需要设置安全目录：`git config --global --add safe.directory /www/wwwroot`
- 9，务必设置好.gitignore文件，防止提交垃圾文件
- 10，缓存当前目录下所有文件：`git add .`
- 11，提交：`git commit -m 本次提交描述文字 `
- 12，推送：`git push`

### Linux更新版本
- 安装 centos7 WANDisco 仓库：`yum install http://opensource.wandisco.com/centos/7/git/x86_64/wandisco-git-release-7-2.noarch.rpm`
- 安装 Git：`yum -y install git`
- 查看git版本：git --version

### 关闭SSL证书验证（报错OpenSSL SSL_read: Connection was reset, errno 10054）
- $ git config --global http.sslVerify "false"

### 正确显示带中文的目录、文件
- git config --global core.quotepath false

### 忽略文件.gitignore
- debug：忽略所有叫debug的文件（无扩展名）和文件夹及其里面所有的文件
- !debug/：排除上一行中的文件夹
- debug/：忽略所有目录下的debug文件夹及里面所有的文件和文件夹
- /debug/：忽略当前目录下的debug文件夹
- *.log：忽略所有的.log后缀文件

### 其他
- 生成一个可供发布的压缩包
- git archive



## 【Git命令大全】
- Workspace：工作区
- Index / Stage：暂存区
- Repository：仓库区（或本地仓库）
- Remote：远程仓库

### 一、新建代码库
- 在当前目录新建一个Git代码库
- git init
- 新建一个目录，将其初始化为Git代码库
- git init [project-name]
- 下载一个项目和它的整个代码历史
- git clone [url]

### 二、配置
- Git的设置文件为.gitconfig，它可以在用户主目录下（全局配置），也可以在项目目录下（项目配置）。
- 显示当前的Git配置
- git config --list
- 编辑Git配置文件
- git config -e [--global]
- 设置提交代码时的用户信息
- git config [--global] user.name "[name]"
- git config [--global] user.email "[email address]”
- git 修改当前的project的用户名的命令为：
- > git config user.name 你的目标用户名;
- git修改当前的project提交邮箱的命令为：
- > git config user.email 你的目标邮箱名;
- 如果你要修改当前全局的用户名和邮箱时，需要在上面的两条命令中添加一个参数，–global，代表的是全局。
- 命令分别为：
- > git config  --global user.name 你的目标用户名；
- > git config  --global user.email 你的目标邮箱名;
- 允许自动保存密码
- >git config --global credential.helper store
- 清除自动保存的密码
- >git config --system --unset credential.helper

### 三、增加/删除文件
- 添加指定文件到暂存区
- - git add [file1] [file2] ...
- 添加指定目录到暂存区，包括子目录
- - git add [dir]
- 添加当前目录的所有文件到暂存区
- - git add .
- 添加每个变化前，都会要求确认
- 对于同一个文件的多处变化，可以实现分次提交
- git add -p
- 删除工作区文件，并且将这次删除放入暂存区
- git rm [file1] [file2] ...
- 停止追踪指定文件，但该文件会保留在工作区
- git rm --cached [file]
- 改名文件，并且将这个改名放入暂存区
- git mv [file-original] [file-renamed]

### 四、代码提交
- 提交暂存区到仓库区
- git commit -m [message]
- 提交暂存区的指定文件到仓库区
- git commit [file1] [file2] ... -m [message]
- 提交工作区自上次commit之后的变化，直接到仓库区
- git commit -a
- 提交时显示所有diff信息
- git commit -v
- 使用一次新的commit，替代上一次提交
- 如果代码没有任何新变化，则用来改写上一次commit的提交信息
- git commit --amend -m [message]
- 重做上一次commit，并包括指定文件的新变化
- git commit --amend [file1] [file2] ...

### 五、分支
- 列出所有本地分支
- git branch
- 列出所有远程分支
- git branch -r
- 列出所有本地分支和远程分支
- git branch -a
- 新建一个分支，但依然停留在当前分支
- git branch [branch-name]
- 新建一个分支，并切换到该分支
- git checkout -b [branch]
git checkout -b appoint_box（别名） origin/feature/20181128_1491627_appoint_box_1（分支名）
- 新建一个分支，指向指定commit
- git branch [branch] [commit]
- 新建一个分支，与指定的远程分支建立追踪关系
- git branch --track [branch] [remote-branch]
- 切换到指定分支，并更新工作区
- git checkout [branch-name]
- 切换到上一个分支
- git checkout -
- 建立追踪关系，在现有分支与指定的远程分支之间
- git branch --set-upstream [branch] [remote-branch]
- 合并指定分支到当前分支
- git merge [branch]
- 选择一个commit，合并进当前分支
- git cherry-pick [commit]
- 删除分支
- git branch -d [branch-name]
- 删除远程分支
- git push origin --delete [branch-name]
- git branch -dr [remote/branch]

### 六、标签
- 列出所有tag
- git tag
- 新建一个tag在当前commit
- git tag [tag]
- 新建一个tag在指定commit
- git tag [tag] [commit]
- 删除本地tag
- git tag -d [tag]
- 删除远程tag
- git push origin :refs/tags/[tagName]
- 查看tag信息
- git show [tag]
- 提交指定tag
- git push [remote] [tag]
- 提交所有tag
- git push [remote] --tags
- 新建一个分支，指向某个tag
- git checkout -b [branch] [tag]

### 七、查看信息
- 显示有变更的文件
- git status
- 显示当前分支的版本历史
- git log
- 显示commit历史，以及每次commit发生变更的文件
- git log --stat
- 搜索提交历史，根据关键词
- git log -S [keyword]
- 显示某个commit之后的所有变动，每个commit占据一行
- git log [tag] HEAD --pretty=format:%s
- 显示某个commit之后的所有变动，其"提交说明"必须符合搜索条件
- git log [tag] HEAD --grep feature
- 显示某个文件的版本历史，包括文件改名
- git log --follow [file]
- git whatchanged [file]
- 显示指定文件相关的每一次diff
- git log -p [file]
- 显示过去5次提交
- git log -5 --pretty --oneline
- 显示所有提交过的用户，按提交次数排序
- git shortlog -sn
- 显示指定文件是什么人在什么时间修改过
- git blame [file]
- 显示暂存区和工作区的代码差异
- git diff
- 显示暂存区和上一个commit的差异
- git diff --cached [file]
- 显示工作区与当前分支最新commit之间的差异
- git diff HEAD
- 显示两次提交之间的差异
- git diff [first-branch]...[second-branch]
- 显示今天你写了多少行代码
- git diff --shortstat "@{0 day ago}"
- 显示某次提交的元数据和内容变化
- git show [commit]
- 显示某次提交发生变化的文件
- git show --name-only [commit]
- 显示某次提交时，某个文件的内容
- git show [commit]:[filename]
- 显示当前分支的最近几次提交
- git reflog
- 可以得到cimmit id
- 从本地master拉取代码更新当前分支：branch 一般为master
- git rebase [branch]

### 八、远程同步
- 更新远程仓储
- git remote update  
- 下载远程仓库的所有变动
- git fetch [remote]
- 显示所有远程仓库
- git remote -v
- 显示某个远程仓库的信息
- git remote show [remote]
- 增加一个新的远程仓库，并命名
- git remote add [shortname] [url]
- 取回远程仓库的变化，并与本地分支合并
- git pull [remote] [branch]
- 上传本地指定分支到远程仓库
- git push [remote] [branch]
- 强行推送当前分支到远程仓库，即使有冲突
- git push [remote] --force
- 推送所有分支到远程仓库
- git push [remote] --all

### 九、撤销
- 恢复暂存区的指定文件到工作区
- git checkout [file]
- 恢复某个commit的指定文件到暂存区和工作区
- git checkout [commit] [file]
- 恢复暂存区的所有文件到工作区
- git checkout .
- 重置暂存区的指定文件，与上一次commit保持一致，但工作区不变
- git reset [file]
- 重置暂存区与工作区，与上一次commit保持一致
- git reset --hard
- 重置当前分支的指针为指定commit，同时重置暂存区，但工作区不变
- git reset [commit]
- 重置当前分支的HEAD为指定commit，同时重置暂存区和工作区，与指定commit一致
- git reset --hard [commit]
- 重置当前HEAD为指定commit，但保持暂存区和工作区不变
- git reset --keep [commit]
- 新建一个commit，用来撤销指定commit
- 后者的所有变化都将被前者抵消，并且应用到当前分支
- git revert [commit]
- 暂时将未提交的变化移除，稍后再移入
- git stash
- git stash pop
