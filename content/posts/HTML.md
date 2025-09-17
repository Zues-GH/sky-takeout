+++
title = 'HTML'
categories = ["前端"]
+++

## 文档结构
```html
<!DOCTYPE html>
<html>
<head>
    <title></title>
</head>
<body>
    <!-- 页面内容 -->
</body>
</html>
```
- \<!DOCTYPE html>是 HTML5 文档的文档类型声明（Document Type Declaration，简称 DTD），它告诉浏览器当前文档使用的是 HTML5 标准
- \<!DOCTYPE html>必须放在第一行，规定不区分大小写
```html
<html>
<head lang="zh-CN">
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title></title>
</head>
<body>
    <!-- 页面内容 -->
</body>
</html>
```
- \<head lang="zh-CN">用于声明文档的主要语言为​​简体中文
- \<meta charset="UTF-8">指定网页的字符编码为 UTF-8
- \<meta name="viewport" content="width=device-width, initial-scale=1.0">用于移动端适配

## 常用标签
- 标题: \<h1>到\<h6>
- 段落: \<p>
- 链接: \<a href="URL">
- 图片: \<img src="URL" alt="描述">
- 列表: \<ul>, \<ol>, \<li>
- 表格: \<table>, \<tr>, \<td>, \<th>
- 表单: \<from>, \<input>, \<textarea>

## 注释
\<!-- 注释内容 -->