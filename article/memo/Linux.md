---
layout: posts
title: Linux 备忘
---


# badblocks 检查磁盘中的坏块

```bash
$ badblocks [-svw] [-b <BLOCKSIZE>] [-o <OUTPUT>] [DISKDIR] [END] [START]
```

- 参数说明: 
    - b <BLOCKSIZE> 指定磁盘的区块大小, 单位为字节
    - o <OUTPUT> 将检查的结果写入指定的输出文件
    - s 检查时显示进度
    - v 执行时显示详细的信息
    - w 检查时执行写入测试 (备份好数据)
    - [DISKDIR] 指定要检查的磁盘装置
    - [END] [START] 指定开始区块和结束区块






# 修改磁盘分区类型 (以 /dev/sdb 为例)

```bash
$ parted /dev/sdb
```
- 输入 `mklabel` 创建新的分区表
- 输入 `gpt` / `msdos` 创建 GPT/MBR 分区表
- `quit` 退出

