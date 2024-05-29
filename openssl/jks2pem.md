- 安装OpenSSL
- 先转为pfx格式，会提示设置pfx文件的密码，如888888，其中123456未存储密码
```
keytool -v -importkeystore -srckeystore demo.jks -srcstoretype jks -srcstorepass 123456 -destkeystore demo.pfx -deststoretype pkcs12 -deststorepass 123456 -destkeypass 123456
```
- 再转为key格式，会提示上一步录入的密码：888888
```
openssl pkcs12 -in demo.pfx -nocerts -nodes -out demo.key
```
- 生成的demo.key里就有pem格式密钥
