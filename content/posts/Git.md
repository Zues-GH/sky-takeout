+++
draft = false
title = 'Git'
weight = 4
+++

## 常用命令
### 初始化仓库
```
git init # 在当前目录创建新仓库

Remove-Item -Recurse -Force .git # 删除仓库(Powershell)
```

### 查看状态
```
git status # 查看当前状态
git log # 查看提交历史
```

### 暂存区
```
git add . # 添加所有文件
git add <文件> # 添加文件
git reset # 撤销git add .操作
git reset <文件> # 撤销git add <文件>操作
```

### 本地仓库 
```
git commit # 提交更改
git commit -m "描述" # 提交更改并说明
```

### 远程仓库
```
git push # 推送更改
git push origin main # 推送更改到main分支

git pull # 拉取更新

git clone <url> # 克隆远程仓库
```
