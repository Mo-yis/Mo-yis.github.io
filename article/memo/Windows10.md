---
layout: posts
title: Windows10 备忘
---


# HASH 计算

- 使用 PowerShell 或 CMD 运行
```powershell
certutil -hashfile <file_name> <type>
```

- 可使用的计算类型有:
	- `sha1`
	- `sha256`
	- `sha384`
	- `sha512`
	- `md5`


