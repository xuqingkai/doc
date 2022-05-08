### 卸载
yum -y remove httpd

会将和httpd有依赖关系的包也一并删除，算是比较干净和省事的卸载方式了，但依然会有遗漏的可能。

可以用 rpm -qa | grep httpd 查看是否有遗漏。 如果有，可以用 rpm -e 包名  删除。

终极查漏的方式： httpd -v   还有 which httpd

### 其他
