- 安装OpenSSL
- 在jks文件所在目录下，执行以下命令，先转为pfx格式文件
- 其中000000为存储密码、111111为别名密码，会提示再次输入密码（第三个），如:222222

```
keytool -v -importkeystore -srckeystore demo.jks -srcstoretype jks -srcstorepass 000000 -destkeystore demo.pfx -deststoretype pkcs12 -deststorepass 000000 -destkeypass 111111
```

- 再进入到OpenSSL安装目录下的bin目录，执行以下代码，转为key格式
- 会提示输入一个密码，也就是前面的存储密码：000000
  
```
./openssl.exe pkcs12 -in demo.pfx -nocerts -nodes -out demo.key
```
- 生成的demo.key里就有pem格式密钥
