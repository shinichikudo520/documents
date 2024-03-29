### 连接远程仓库

1. 参加文件夹
2. `git init`
3. `git config --global user.name " " （写用户名）`
4. `git config --global user.email " " （ 写用户邮箱）`
5. `ssh-keygen -t rsa -C " " （写上邮箱） 生成密钥`
6. 获取秘钥：`cat ~/.ssh/id_rsa.pub`
7. 上 git 添加秘钥
8. `git remote add origin https://github.com/shinichikudo520/***.git`
9. `git pull origin master`

### ssl 连接错误

![ssl连接错误](./img/SSL_connect.png)

- 解决:

```
git config --global http.sslVerify "false"
git config --global https.sslVerify "false"
```

### time out 错误

![ssl连接错误](./img/timeout.png)

- 解决：

```
git config --global --unset http.proxy
git config --global --unset https.proxy
```

### 生成 ssh 并提交到 github 之后仍然报错

    fatal: Could not read from remote repository.

- 解决:

  1. 找到路径, **C:\Users\hubiyu\.ssh**
  2. 参加一个文件, **config**
  3. 填写以下内容

  ```
    Host github.com
    User git
    Hostname ssh.github.com
    PreferredAuthentications publickey
    IdentityFile ~/.ssh/id_rsa
    Port 443

    Host gitlab.com
    Hostname altssh.gitlab.com
    User git
    Port 443
    PreferredAuthentications publickey
    IdentityFile ~/.ssh/id_rsa
  ```
