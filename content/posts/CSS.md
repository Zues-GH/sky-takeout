+++
title = 'CSS'
categories = ["前端"]
+++

## CSS引入
1. 内敛样式（Inline Style）
在HTML标签的style属性编写CSS
```
<p style="color: blue;">这是一个蓝色的段落。</p>
```
- 难以维护，不推荐大量使用

2. 内部样式（Internal Style）
在<head>部分使用<style>标签编写CSS
```
<head>
    <style>
        p {
            color: blue;
            font-size: 16px;
        }
    </style>
</head>
<body>
    <p>这是一个蓝色的段落。</p>
</body>
```
- 适用于单个页面

3. 内部样式（External Style）
在独立的css文件编写CSS，然后在HTML中通过<link>标签引入
```css{title="style.css"}
/* style.css */
p {
    color: blue;
}
```

```html{title="index.html"}
<head>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <p>这是一个蓝色的段落。</p>
</body>
```
- 适用于多个页面共享管理

## CSS语法结构
CSS规则集（Rule Set）：选择器 + 声明块
```
选择器 {
    属性: 值;
    属性: 值;
}
/* 示例 */
p {
    color: blue;      /* 文字颜色为蓝色 */
}
```
- 选择器（Selector）：p（选中想要样式化的HTML元素）
- 声明（Declaration）：color：blue（完整声明）
- 属性（Property）：color（想要改变的样式）
- 值（Value）：red（想要改变的样式值）
- 声明块：花括号{}包裹所有声明

### 选择器
| 表头1 | 表头2 | 表头3 |
|-------|-------|-------|
| 内容1 | 内容2 | 内容3 |
| 内容4 | 内容5 | 内容6 |


|选择器|写法|示例|示例说明|
|:----:|:--:|:--:|:------:|
|元素选择器|元素名称 {...}|h1 {...}|选择页面上所有的<h1>标签|



1. 元素选择器
HTML标签名
```css
p { }  /* 选中所有 <p> 标签 */
```
2. 类选择器
. + 类名
```css
.highlight { background-color: yellow; }
```

```html
<p class="highlight">这个段落会被高亮</p>
<div class="highlight">这个div也会被高亮</div>
```
- 最常用的选择器

3. ID选择器
\# + id名
```css
#header { height: 100px; }
```

```html
<div id="header">这是顶部栏</div>
```
- ​​一个页面中同一 ID 只能出现一次​​，通常用于唯一性元素

4. 后代选择器
用于选择特定元素内部的元素
```css
/* 只选择在 article 元素内部的 p 元素 */
article p { color: gray; }
```

## 盒模型（Box Model）
每个元素都被表示为一个矩形盒子,由4个部分组成：
内容  (Content)
内边距 (Padding)
边框  (Border)
外边距 (Margin)
![](https://www.w3schools.com/css/box-model.gif)

## 一维布局Flexbox
```css
/* 成为Flex容器 */
.container {
    display: flex;
}
```
- justify-content: (center, space-between, space-around)【横轴对齐】

- align-items: ​(center, stretch, flex-start)【竖轴对齐】
- 常用于水平垂直居中功能
- 子元素继承父元素的Flex属性

## 二位布局Grid
```css
/* 成为grid容器 */
.container {
    display: grid
}
```
- 子元素继承父元素的Grid属性

### 网格轨道（Grid Tracks）
```css
.grid-container {
    display: grid;
    grid-template-columns: 100px 200px 100px; /* 3列，宽度分别为100px, 200px, 100px */
    grid-template-rows: 100px 200px; /* 2行，高度分别为100px, 200px */
}
```
- 行（row）：水平方向的轨道
- 列（column）：垂直方向的轨道

### 网格线（Grid Lines）
```
┌───┬───────┬───┐
│ ■ │       │   │
├───┼───────┼───┤
│   │       │   │
└───┴───────┴───┘
```