### 运算命令符：【&】【&&】【|】【||】【；】   
- &  表示程序要在后台运行。方式：command1 &
- &&  逻辑“与”，表示前一条命令执行成功时，才执行后一条命令；如果前面一条命令执行失败，后面的命令不再执行。方式：command1 && command2
- |  管道符，表示上一条命令的输出，作为下一条命令参数进行传递。方式：command1 | command2
- ||  逻辑“或”，表示前一条命令执行成功时，后一条命令不再执行；如果前面一条命令执行失败，后面的命令再执行。方式：command1 || command2
- ;(英文分号;)  表示每个命令按照从左到右的顺序来执行，每个命令彼此之间无任何关联，所有命令都要执行。方式：command1;command2

### 切换为root，并改密为1234qwer

sudo -i  
echo root:1234qwer |chpasswd root  
sed -i 's/^#\?PermitRootLogin.*/PermitRootLogin yes/g' /etc/ssh/sshd_config;  
sed -i 's/^#\?PasswordAuthentication.*/PasswordAuthentication yes/g' /etc/ssh/sshd_config;  
service sshd restart  

### 设置密码：给当前账户改密码需要验证当前密码，否则不需要
给root设置密码：sudo passwd root  
切换到root用户：su root  
再给ubuntu设置密码：sudo passwd ubuntu  
查看sshd服务：netstat -anp | grep sshd  
重启sshd服务：service sshd restart 或 /etc/init.d/sshd restart  

### 配置允许账号方式登录：/etc/ssh/sshd_config
赋予读写权限：sudo chmod 777 /etc/ssh/sshd_config  
打开配置文件：vi /etc/ssh/sshd_config  
开启普通账号密码登录：PasswordAuthentication yes  
允许root账号密码登录：PermitRootLogin yes  
以上两条，没有就手工加上  
改回读写权限：sudo chmod 644 /etc/ssh/sshd_config  
重启服务：sudo service sshd restart  


### 系统：uname --help
查看系统信息：uname -a


### Centos防火墙

启动防火墙服务：systemctl start firewalld  
停止防火墙服务：systemctl stop firewalld  
启用防火墙服务开机启动：systemctl enable firewalld  
禁用防火墙服务开机启动：systemctl disable firewalld  
查看防火墙服务运行状态：systemctl status firewalld -l  

查看所有防火墙服务清单：firewall-cmd --list-all  
查看防火墙所有已开放端口：firewall-cmd --list-ports --permanent  
查看防火墙是否开放8888端口：firewall-cmd --query-port=8888/tcp  
打开防火墙8888端口：firewall-cmd --add-port=8888/tcp --permanent  
打开防火墙8080-8090端口：firewall-cmd --add-port=8080-8090/tcp --permanent  
移除防火墙8888端口：firewall-cmd --remove-port=8888/tcp --permanent  
务必重载防火墙配置：firewall-cmd --reload  

### 端口
查看3306端口占用情况：netstat -untlp | grep 3306  

释放端口：kill -9 进程pid号

### 卸载jdk包
查询：rpm -qa|grep jdk  
显示：jdk-1.7.0_71-fcs.x86_64  
卸载：rpm -e --nodeps jdk-1.7.0_71-fcs.x86_64  

### socat

- centos/redhat：
``` yum install -y socat ```
- debian/ubuntu：
``` apt-get install socat ```

