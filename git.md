### ssl连接错误
![ssl连接错误](./img/SSL_connect.png)
解决:
```
git config --global http.sslVerify "false"
git config --global https.sslVerify "false"
```

### time out错误
解决：
```
git config --global --unset http.proxy
git config --global --unset https.proxy
```
