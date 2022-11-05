---
layout: posts
title: SSH 备忘
---


# 配置 SSH Key

1. 执行以下命令, 删除旧代理:

```bash
$ ssh-add -D && ssh-add -l
```

2. 新建单个 SSH Key:

```bash
$ ssh-keygen -t rsa -C "example@example.com"
```

3. 编辑 `~/.ssh/config` 添加以下内容:

```bash
Host github.com
    Hostname        github.com
    User            git
    IdentityFile    ~/.ssh/id_rsa
    ProxyCommand    ncat --proxy 127.0.0.1:1089 --proxy-type socks5 %h %p
```

- Key 文件存放于 `~/.ssh/` 目录下

4. 公钥是以 `.pub` 为后缀的文件, 获取远程服务器的公钥 SSH Key:

```bash
$ cat ~/.ssh/id_rsa.pub
```

- 配置文件 `config` 用于指定 Key 的账户信息:
    - Host:         设置主机别名, 标识不同的 Key, 用于替换 HostName.
    - HostName:     网站的域名, 即 SSH 连接的对应网站域名.
    - User:         远程服务器的登陆用户名.
    - IdentityFile: SSH Key 的文件位置.
    - ProxyCommand: 使用代理命令 (**可选**)
- `ncat` 是一个通用的 CLI 工具, 用于在网络上读取\写入和重定向数据:
    - `--proxy <addr[:port]>` 指定代理主机和端口
    - `--proxy-type <type>` 指定代理类型 ("http", "socks4", "socks5")









# 配置多个 SSH Key

1. 执行以下命令, 删除旧代理:
```
$ ssh-add -D && ssh-add -l
```

2. 按需要新建多个 SSH Key (以 `com` 和 `net` 为例):
```
$ ssh-keygen -t rsa -C "example@example.com" -f ~/.ssh/com
$ ssh-keygen -t rsa -C "example@example.net" -f ~/.ssh/net
```

3. 编辑 `~/.ssh/config` 添加以下内容:
```
Host com
    HostName        github.com
    User            git
    IdentityFile    ~/.ssh/com
    ProxyCommand    ncat --proxy 127.0.0.1:1089 --proxy-type socks5 %h %p

Host net
    HostName        github.com
    User            git
    IdentityFile    ~/.ssh/net
    ProxyCommand    ncat --proxy 127.0.0.1:1089 --proxy-type socks5 %h %p
```
- 参数 `-f` 用于指定 Key 的名称, 默认为 `id_rsa`.







# 测试 SSH 连接

- 测试远程服务器连通性 (服务器以 github.com 为例, 用户为 git):
```
$ ssh -T git@github.com
```

- 若有多个 SSH Key, 需按对应主机别名测试 (以 `com` 和 `net` 为例):
```
$ ssh -T git@com
$ ssh -T git@net
```

