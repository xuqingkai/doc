### 最新下载地址
- https://downloads.mysql.com/archives/installer/
### 卸载
- yum remove mysql mysql-server mysql-libs compat-mysql51
- rm -rf /var/lib/mysql
- rm /etc/my.cnf
- 查看是否还有mysql软件：
- rpm -qa|grep mysql
- which mysql
- mysql -V
- 以上三条命令如果有返回信息的话就说明还没有删除干净，继续搜索文件删除
