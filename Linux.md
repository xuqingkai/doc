### 切换为root，并改密为1234qwer

sudo -i  
echo root:1234qwer |chpasswd root  
sed -i 's/^#\?PermitRootLogin.*/PermitRootLogin yes/g' /etc/ssh/sshd_config;  
sed -i 's/^#\?PasswordAuthentication.*/PasswordAuthentication yes/g' /etc/ssh/sshd_config;  
service sshd restart  

### 系统：
查看系统信息：uname --help


### 防火墙

启动防火墙服务：systemctl start firewalld  
停止防火墙服务：systemctl stop firewalld  
启用防火墙服务开机启动：systemctl enable firewalld  
禁用防火墙服务开机启动：systemctl disable firewalld  
查看防火墙服务运行状态：systemctl status firewalld -l  

查看所有防火墙服务清单：firewall-cmd --list-all  
查看防火墙所有已开放端口：firewall-cmd --list-ports --permanent  
查看防火墙是否开放8888端口：firewall-cmd --query-port=8888/tcp  
打开防火墙8888端口：firewall-cmd --add-port=8888/tcp --permanent  
移除防火墙8888端口：firewall-cmd --remove-port=8888/tcp --permanent  
重新载入防火墙配置：firewall-cmd --reload  

### 端口
查看3306端口占用情况：netstat -untlp | grep 3306  

### 卸载jdk包
查询：rpm -qa|grep jdk  
显示：jdk-1.7.0_71-fcs.x86_64  
卸载：rpm -e --nodeps jdk-1.7.0_71-fcs.x86_64  

### socat

- centos/redhat：
``` yum install -y socat ```
- debian/ubuntu：
``` apt-get install socat ```

