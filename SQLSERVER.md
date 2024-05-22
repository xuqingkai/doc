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

### 附加数据库
- 找到要迁移的数据，
- 右键单击，任务，脱机
- 
- 复制数据库文件（mdf后缀）到新服务器
- 在新服务器上打开数据库管理客户端
- 在“数据库”三个字上，右键点击，附加

- 在“要附加的数据库”选项卡，
- 检查MDF文件的位置是否正确，如果不正确，重新指定下
- 双击“附加为”更改为你要想要的新数据库名

- 在“XXX数据库详细信息”选项卡
- 检查MDF文件的位置是否正确，如果不正确，重新指定下
- 选中“LDF文件”一行，删除，

- 确定，即可迁移完毕
- 如果提示附加失败，一般是原数据没有在完全停止的情况下就复制过来了

### 还原数据库
- 打开数据库管理软件
- 在“数据库”三个字上点右键，选择“还原数据库”
- 在打开的对话框里，
- 【常规】选项卡，目标数据库输入新的数据库名称
- 【文件】选项卡，选中“将所有文件重新定位到文件夹”，
- 将数据库文件夹和日志文件文件夹设定为新的保存路径
- 同时，在下面文件列表里，修改“还原为”这一列的值为新的数据库文件名和日志文件名
- 【选项】选项卡，根据实际需要，选中“覆盖现有数据库”
- 确定，即可还原为一个新的数据库
- 为了更完美，右键点击新数据库，选择属性，选择【文件】选项卡，
- 在文件列表里，把文件的“逻辑名称”修改为对应的名称

### 设计视图增加默认值和说明列
- 1，打开注册表
```
HKEY_CURRENT_USER\Software\Microsoft\SQL Server Management Studio\11.0\DataProject”
```
- 注意这里的11.0表示安装的SQL Server Management Studio版本号。
- SQL Server 2008 R2则对应10.0，
- SQL Server 2012/2014对应11.0
- SQL Server 2019，路径变为：`Computer\HKEY_CURRENT_USER\Software\Microsoft\SQL Server Management Studio\18.0_IsoShell\DataProject`

- 2，找到 SSVPropViewColumnsSQL70 和SSVPropViewColumnsSQL80。
- 先关闭sqlserver管理工具然后将默认值“1,2,6;”改为“1,2,6,7,17;”
- 再次打开管理器，即可


- 各数字代表的意思如下：
```
1:Column Name
2:Data Type
3:Length
4:Precision
5:Scale
6:Allow Nulls
7:Default Value
8:Identity
9:Identity Seed
10:Identity Increment
11:Row GUID
12:Nullable
13:Condensed Type
14:Not for Replication
15:Formula
16:Collation
17:Description
```

### 移动数据库到别的服务器
- 1，建立同名空数据库
- 2，还原数据库
- 3，建立同名登录
- 4，执行：use sq_galadou exec sp_change_users_login 'update_one','sq_galadou','sq_galadou'

### 查询结果，复制出来无回车符效果
- 工具/选项/查询结果/SQL Server/以网格显示结果/复制或保存时保留CR/LF(E)，勾选后，重启SMSS即可

### 将数据库调整为支持中文，否则数据库中存入中文字符串会变成问号
- 数据库，右键，选项，维护，排序规则，Chinese_PRC_90_CI_AS
- ALTER DATABASE xqk_test COLLATE Chinese_PRC_90_CI_AS

### 补货异常
```
BEGIN TRY
-- 你的sql
END TRY
BEGIN CATCH
    SELECT
        ERROR_NUMBER() AS ErrorNumber,
        ERROR_MESSAGE() AS ErrorMessage;
END CATCH
```
