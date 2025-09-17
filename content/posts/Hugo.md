+++
title = 'Hugo'
weight = 1
categories = ["博客"]
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

### markdown配置
[markup.goldmark.renderer]
hardWraps = true # 启用markdown中回车即换行