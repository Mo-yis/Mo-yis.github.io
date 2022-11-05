---
layout: posts
title: Ubuntu20 个人配置
---


# 隐藏 Trash 和 $HOME

```bash
$ gsettings set org.gnome.shell.extensions.desktop-icons show-trash false
$ gsettings set org.gnome.shell.extensions.desktop-icons show-home  false
```



# 安装常用软件

## 安装 VirtualBox

```bash
$ sudo apt install virtualbox virtualbox-ext-pack virtualbox-guest-additions-iso
```

- 此操作会安装 VirtualBox 及其常用工具.

## 安装 FFmpeg Aria2 Vim

```bash
$ sudo apt install ffmpeg aria2 vim
```
