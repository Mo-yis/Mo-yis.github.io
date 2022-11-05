---
layout: posts
title: VirtualBox 个人配置
---


# 配置 VirtualBox

1. 安装 VirtualBox

2. 将自己添加到 vboxusers 组

```bash
$ sudo usermod -aG vboxusers $USER
```

3. 检查状态

```bash
$ cat /etc/group | grep vboxusers
```






# VirtualBox 引导U盘启动系统 (**Win10不支持UEFI启动, 推荐 Ventoy 启动虚拟硬盘**)

1. 确认U盘位置

```bash
$ sudo fdisk -l
```

2. 为U盘添加访问权限 (以 /dev/sdb 为例) 并检查状态

```bash
$ sudo chmod 777 /dev/sdb && ls -l /dev/sdb
```

- 插入的U盘为 root 权限, 为了让 VirtualBox 能映射出虚拟磁盘, 需要以此设置可访问权限.
- 拔出U盘后, 此修改会被重置.

3.  创建U盘需要映射的虚拟磁盘 USB.vmdk:

```bash
$ sudo VBoxManage internalcommands createrawvmdk -filename ~/VirtualBox\ VMs/USB.vmdk -rawdisk /dev/sdb
```

4. 设置虚拟磁盘 USB.vmdk 的组和权限为自己:

```bash
$ sudo chown $(whoami) ~/VirtualBox\ VMs/USB.vmdk && sudo chgrp $(whoami) ~/VirtualBox\ VMs/USB.vmdk
```

- USB.vmdk 默认组和权限是 root, 需要修改为自己使用 VirtualBox 时可访问的权限.

5.  检查状态:

```bash
$ ls -l ~/VirtualBox\ VMs/USB.vmdk
```

- 之后创建虚拟机时选择已存在的虚拟硬盘为 USB.vmdk 即可.

