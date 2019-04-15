- 生成私钥和证书
```bash
# 生成2048位的rsa私钥
openssl genrsa -out private.pem 2048

# -new 新的证书请求
# -key 指定私钥文件
openssl req -new -key private.pem -out cert.req

# 会自动生成2018位的rsa私钥
openssl req -new -out cert.req

# x509 证书格式
# -req -in 将input作为证书请求
# -signkey 自签名的私钥
# -days 证书过期时间，def 30
openssl x509 -req -in cert.req -signkey private.pem -out foo.crt -days 365
```