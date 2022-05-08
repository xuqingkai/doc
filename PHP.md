### 取消php和phpMyAdmin上传最大2M文件限制


“当用 phpMyAdmin 导入的数据库大小大于 2M 的时候，会出现如下提示：
No data was received to import. Either no file name was submitted, or the file size exceeded the maximum size permitted by your PHP configuration. See FAQ 1.16.”

【解决方法】：

一、修改c:\windows\php.ini文件。
用写字板打开php.ini文件：
1、查找post_max_size，指通过表单POST给PHP的所能接收的最大值，包括表单里的所有值，默认为8M，看你自己需要进行改变。
2、查找File Uploads，首先确认file_uploads = on ;是否允许通过HTTP上传文件的开关，默认为ON即是开。 upload_tmp_dir ; 
查找upload_max_filesize ;即允许上传文件大小的最大值。默认为2M。
3、如果要上传>8M的文件，那么只设置上述四项还不定一定可以。最好对下面的参数也进行设置： 
查找max_execution_time = 600 ;每个PHP页面运行的最大时间值(秒)，默认30秒。 
max_input_time = 600 ;每个PHP页面接收数据所需的最大时间，默认60秒 。
memory_limit = 8M ;每个PHP页面所吃掉的最大内存，默认8M。

二、修改c:\phpmyadmin\import.php文件。
用写字板打开import.php文件：
1、查找$memory_limit，默认为$memory_limit = 2 * 1024 * 1024;自己修改。
2、下边三四行的位置有同样的语句，自己修改。

三、到这里还不行，IIS的问题。

1）解决在 IIS 6.0 中，无法上传大容量文件的办法：
1、先在服务里关闭 iis admin service 服务。
2、找到 windows\system32\inetsrv\ 下的 metabase.xml 文件。
3、用写字板打开，找到 ASPMaxRequestEntityAllowed 把它修改为需要的值（默认为：204800，即：200K）。
4、存盘，然后重启 iis admin service 服务，重启IIS。

2）解决在 IIS 6.0 中，无法下载超过4M的附件步骤：
1、先在服务里关闭 iis admin service 服务。
2、找到 windows\system32\inetsrv\ 下的 metabase.xml 文件。
3、用写字板打开，找到 AspBufferingLimit 把它修改为需要的值（默认为：4194304，即：4MB）。
4、存盘，然后重启 iis admin service 服务，重启IIS。

OK，有以上三步，PHP的2M限制完全搞定！

### 卸载

先用rpm -qa | grep php 查看全部依赖包，再用命令 rpm -e 包名 将它们一一删除。 删除时会提示依赖关系，提示那个包就先那个包即可。

大概顺序如下：
rpm -e php-fpm-5.3.3-22.el6.x86_64

rpm-e php-pdo-5.3.3-22.el6.x86_64

rpm -e php-pear-1.9.4-4.el6.noarch

rpm-e php-cli-5.3.3-22.el6.x86_64

rpm -e php-5.3.3-22.el6.x86_64

rpm-e php-xml-5.3.3-22.el6.x86_64

rpm -e php-gd-5.3.3-22.el6.x86_64

rpm-e php-common-5.3.3-22.el6.x86_64

干净删除mysql
