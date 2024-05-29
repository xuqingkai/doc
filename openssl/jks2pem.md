- 安装OpenSSL
- 在jks文件所在目录下，执行以下命令，先转为pfx格式文件
- 其中000000为存储密码、111111为别名密码，会提示再次输入别名密码，如:111111

```
keytool -v -importkeystore -srckeystore demo.jks -srcstoretype jks -srcstorepass 000000 -destkeystore demo.pfx -deststoretype pkcs12 -deststorepass 000000 -destkeypass 111111
```

- 再进入到OpenSSL安装目录下的bin目录，执行以下代码，转为key格式
- 会提示设置一个密码，随便设置一个6位数字如123456，记住即可
  
```
./openssl.exe pkcs12 -in demo.pfx -nocerts -nodes -out demo.key
```
- 生成的demo.key里就有pem格式密钥
