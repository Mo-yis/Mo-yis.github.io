---
layout: posts
title: Vim 个人配置
---

```
" 配置 ~/.vimrc 文件

set tabstop=4       " Tab 为4空格
set softtabstop=4   " Backspace 为4空格
set shiftwidth=4    " 每级缩进长度为4空格
set expandtab       " Tab 为空格符 (noexpandtab 为制表符)
set autoindent      " 自动缩进

set number          " 显示行号
set showmatch       " 高亮匹配的括号
set laststatus=1    " 1 启用时显示状态行, 2 总是显示状态行
set ruler           " 显示光标所在坐标
set incsearch       " 搜索输入高亮
set hlsearch        " 搜索结果高亮

syntax enable       " 语法高亮

" \ + 空格 退出搜索结果高亮
nnoremap <silent><space> :nohlsearch<CR>
```
