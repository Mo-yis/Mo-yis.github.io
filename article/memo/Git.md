---
layout: posts
title: Git 备忘
---


# 配置用户名和邮箱

```bash
$ git config --global user.name "example"
$ git config --global user.email "example@example.org"
```

- 参数 `--global` 设置当前用户的全局配置
- 全局配置保存在 `~/.gitconfig` 文件中




# 检查状态

```bash
$ git config -l
```

- 检查当前仓库配置, 若无配置, 则检查全局配置.

