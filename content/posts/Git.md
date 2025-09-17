+++
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
git remote add origin [远程仓库URL] # 关联远程仓库
git push origin main/master # 推送更改到main/master分支
git push --force-with-lease origin main # 本地分支覆盖远程分支

git pull # 拉取更新


git clone <url> # 克隆远程仓库
```

### CR/LF配置
```
CR/LF混合：
1. Unix/Mac系统下的文件在Windows里打开的话，所有文字会变成一行
2. 而Windows里的文件在Unix/Mac下打开的话，在每行的结尾可能会多出一个^M符号
3. Linux保存的文件在windows上用记事本看的话会出现黑点

git config --global core.autocrlf true # 提交时转换为LF，检出时转换为CRLF
git config core.autocrlf false # 做任何改变，文本文件保持其原来的样子
git config core.autocrlf input # add时Git会把CRLF转换为LF，而check时仍旧为LF，Windows操作系统不建议设置此值。
```
