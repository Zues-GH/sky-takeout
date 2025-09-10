+++
draft = false
title = 'Hugo'
weight = 1
+++

## 常用命令
### 创建博客
hugo new site blog  
cd blog

### 创建页面
hugo new posts/文章.md

### 本地预览
hugo server  
hugo server --gc

### 删除publice目录
Remove-Item -Recurse -Force public