### CENTOS

开启防火墙服务：systemctl start firewalld  
关闭防火墙服务：systemctl stop firewalld  
设置防火墙服务开机启动：systemctl enable firewalld  
禁止防火墙服务开机启动systemctl disable firewalld.service  
查看防火墙服务状态：systemctl status firewalld -l  

查看所有防火墙服务：firewall-cmd --list-all  
查看防火墙所有开放端口：firewall-cmd --list-ports  
查看XX端口是否开放：firewall-cmd --permanent --query-port=80/tcp  
添加80端口：firewall-cmd --add-port=80/tcp --permanent  
移除80端口：firewall-cmd --remove-port=80/tcp --permanent  
重新载入防火墙配置：firewall-cmd --reload  

