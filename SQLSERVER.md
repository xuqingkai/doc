### ID自动递增归零
- 选中指定数据库，新建查询
- 执行命令：`dbcc checkident('表名',RESEED,0);`

### 还原数据库
- 孤立帐户的产生一般是一下两种：
- 1.将备份的数据库在其它机器上还原；
- 2.重装系统或SQL SERVER之后只还原了用户库
- 解决方法是使用sp_change_users_login来修复。
- sp_change_users_login的用法有三种
- 用法1：
- exec sp_change_users_login 'REPORT'列出当前数据库的孤立用户，
- 用法2：
- exec sp_change_users_login 'AUTO_FIX','用户名'
- 可以自动将用户名所对应的同名登录添加到syslogins中，
- 用法3：
- exec sp_change_users_login 'UPDATE_ONE','用户名','登录名'
- 或者: sp_change_users_login 'UPDATE_ONE','用户名','登录名'
- 将用户名映射为指定的登录名。

### 新建数据库专用账号
- 打开服务器管理软件
- 在“安全性”上左键点击，打开子菜单，找到“登录名”，右键选择“新建登录名”
- 【常规】选项卡。选择Sqlserver身份认证，即创建sql登录账户，而不是创建window帐号，最下面，指定数据库，即设置为该数据库的帐号
- 【服务器角色】选项卡不要选择，默认public
- 【用户映射】选项卡，选择对应数据库，
- 其他默认，确定即可创建
- 找到刚才的数据库，点开子菜单，找到最后一项“安全性”，点开“用户”子菜单
- 找到刚才创建的用户，右键选择属性
- 【拥有的架构】选项卡，选择“db_owner”
- 【成员身份】选项卡，也选择“db_owner”
- 确定，全部操作完毕

### 版本到期17051错误
- SQL2008无法启动,这是错误日志：
```
C:/Program Files/Microsoft SQL Server/MSSQL10_50.MSSQLSERVER/MSSQL/Log
2011-06-01 12:16:35.44 Server      Error: 17051, Severity: 16, State: 1.
2011-06-01 12:16:35.44 Server      SQL Server evaluation period has expired.
```
- 解决方法 : 
- 现象：安装的是SQL Server 2008评估版，180天的试用期后，MSSQLSERVER服务就无法启动，手动启动就报告17051错误。

#### 解决办法：
- 第一步：进入SQL2008配置工具中的安装中心，
- 第二步：再进入维护界面，选择版本升级，
- 第三步：进入产品密钥，输入密钥
```
Developer: PTTFM-X467G-P7RH2-3Q6CG-4DMYB
Enterprise: JD8Y6-HQG69-P9H84-XDTPG-34MBB
```
- 第四步：一直点下一步，直到升级完毕。
- 用key升级成功后即可启动MSSQLSERVER服务。如果启动SQL SERVER管理器依然报告过期错误，则将注册表HKEY_LOCAL_MACHINE\SOFTWARE\\Microsoft\Microsoft SQL Server\100\ConfigurationState，将其中CommonFiles的键值改为3。
- 然后再重复以上四个步骤，进行升级就OK了。


