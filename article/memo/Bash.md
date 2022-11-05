---
layout: posts
title: Bash 个人配置
---


# 配置命令行代理

- 编辑 ~/.bashrc 添加以下代码:

```bash
# Custom proxy
export https_proxy=http://127.0.0.1:8889
export http_proxy=http://127.0.0.1:8889
export all_proxy=socks5://127.0.0.1:1089
```

- **此配置对 SSH 协议无效, 需另外配置**






# 启用 Powerline

1. 首先安装Powerline
2. 在 .bashrc 中添加:

```bash
# Powerline
if [ -f `which powerline-daemon` ]; then
  powerline-daemon -q
  POWERLINE_BASH_CONTINUATION=1
  POWERLINE_BASH_SELECT=1
  . /usr/share/powerline/bash/powerline.sh
fi
```







# 自定义命令

- 打开 Bash 配置文件:

```bash
$ vi ~/.bashrc
```

- 公用配置在 /etc/bash.bashrc 文件, 此处为单个用户设置.


## 简化 `ls -alh` 的命令

```bash
alias ll="ls -alh"
```


## 修改 rm 命令

```bash
# 修改rm命令将文件删除至回收站
alias rm=trash
trash(){
    del_date=`date +%Y%m%d%H%M%S`
    # 循环是因为可能rm多个文件
    for arg in "$@"
    do
       # 这里将删除时间加入到文件名后是因为mv命令不能覆盖非空目录以及不能使用文件覆盖文件夹
       # 加上时间就不会有同名的文件了
       mv $arg /tmp/$arg-${del_date}
    done
}
```

- 修改并重新加载后不能使用 rm 的参数.
- rm 只能删除当前目录中的文件或目录.






# 加载 .bashrc 的修改

```bash
$ source ~/.bashrc
```

