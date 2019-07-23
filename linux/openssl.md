- 生成私钥
```bash
# 生成2048位的rsa私钥, 不加密私钥
openssl genrsa -out private.key 2048 # 4096

# 需要设置密码, nginx启动时需要输入密码
openssl genrsa -des3 -out server.key

# 解密得到原始私钥, 相当于不设置-des3
cp server.key server.key.copy
openssl rsa -in server.key.copy -out server.key
```
- 生成证书请求、证书
```bash
# -new 新的证书请求
# -key 指定私钥文件
openssl req -new -key server.key -out server.csr

# 会自动生成2048位的rsa私钥
openssl req -new -out server.csr

# x509 证书格式
# -req -in 将input作为证书请求
# -signkey 自签名的私钥
# -days 证书过期时间
openssl x509 -req -days 365 -in server.csr -signkey server.key -out server.crt
```
- 格式转换
```bash
# pfx格式, IIS中使用
$openssl pkcs12 -export -inkey server.key -in server.crt -out server.pfx

# pem格式
$cat server.crt server.key > server.pem

# pfx -> pem
$openssl pkcs12 -in server.pfx -nodes -out server.pem

# pem -> x509和rsa
$openssl rsa -in server.pem -out server2.key
$openssl x509 -in server.pem -out server2.crt
```

*参考：https://sundoctor.iteye.com/blog/584927*
