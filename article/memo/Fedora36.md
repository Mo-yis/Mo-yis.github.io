---
layout: posts
title: Fedora36 个人配置
---


# 启用 RPM Fusion 存储库

1. 启用自由存储库:

```bash
$ sudo dnf install https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm
```

2. 启用非自由存储库 (**可选**):

```bash
$ sudo dnf install https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
```

3. 首次尝试从这些存储库安装软件包时, DNF 会提示您确认存储库的签名, 确认它

4. 从 RPM Fusion 存储库启用 Appstream 数据:

```bash
$ sudo dnf group update core
```




# 启用 Flatpak 存储库

- 启用 Flathub 存储库:

```bash
$ sudo flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

- 启用上海交通大学 (sjtu) 的 Flathub 镜像存储库:

```bash
$ sudo flatpak remote-add --if-not-exists sjtu  https://mirror.sjtu.edu.cn/flathub/flathub.flatpakrepo
```

- 设置 Flathub 镜像 (如果不是上海交通大学源):

```bash
$ sudo flatpak remote-modify flathub --url=https://mirror.sjtu.edu.cn/flathub
```




# 安装常用软件

## 安装 VLC OBS PowerLine TorBrowser Clash npm Yarn Java

```bash
$ sudo dnf install vlc obs-studio powerline torbrowser-launcher clash npm yarnpkg java-17-openjdk-devel
```

## 安装 VirtualBox

1. 安装 VirtualBox:

```
$ sudo dnf install VirtualBox
```

2. 将自己添加到 vboxusers 组

```
$ sudo usermod -aG vboxusers $USER
$ cat /etc/group | grep vboxusers
```


## 安装 Obsidian

```
$ flatpak install flathub md.obsidian.Obsidian
```

## 安装 VSCodium

1. 添加存储库的 GPG key:

```
$ sudo rpmkeys --import https://gitlab.com/paulcarroty/vscodium-deb-rpm-repo/-/raw/master/pub.gpg
```

2. 添加存储库:

```
$ printf "[gitlab.com_paulcarroty_vscodium_repo]\nname=download.vscodium.com\nbaseurl=https://download.vscodium.com/rpms/\nenabled=1\ngpgcheck=1\nrepo_gpgcheck=1\ngpgkey=https://gitlab.com/paulcarroty/vscodium-deb-rpm-repo/-/raw/master/pub.gpg\nmetadata_expire=1h" | sudo tee -a /etc/yum.repos.d/vscodium.repo
```

3. 安装软件 (如果你想用 vscodium-insiders, 请用 `codium-insiders` 替代 `codium`):

```
$ sudo dnf install codium
```






# 安装不常用软件

## 安装 KDE Plasma 桌面 (**慎重**)

```bash
$ sudo dnf groupinstall "KDE Plasma Workspaces"
$ reboot
```

# 安装 Hydrapaper

```
$ flatpak install flathub org.gabmus.hydrapaper
```

# 安装 ghostwriter

```
$ sudo dnf install ghostwriter
```

