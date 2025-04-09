---
title: 使用 Markdown 写作 ospp 项目申请书
date: 2024-06-05
tags: 
- ospp
- markdown
categories: 
- 技术
---
# 使用 Markdown 写作 ospp 项目申请书

## 项目申请书示例解析

[项目申请书示例](/downloads/项目申请书示例.pdf)

### 标题

标题居中对齐，Markdown 没有原生的语法支持，这里考虑使用 html 语法实现：

```html
<h1>项目申请书</h1> <br>
<h4>项目名称：通过 GitHub Actions 实现标准流程自动化</h4>
<h4>项目主导师：欧阳文</h4>
<h4>申请人：樊漆亮</h4>
<h4>日期：2021.05.04</h4>
<h4>邮箱：fanqiliang@torch-fan.site</h4>
```

也可以在导出 pdf 文件之后使用 Word 或者 Adobe acrobat 等 pdf 编辑工具后期添加

### 目录

原作者使用的是 Typora 自带的目录生成功能，笔者则使用开源的 Markdown Preview Enhanced 插件生成目录。打开 VScode，按下 `Ctrl + shift + x` 搜索插件 `Markdown Preview Enhanced`，点击安装。打开 md 文档，在编辑模式下将光标置于你想要插入目录的位置，按下 `Ctrl + shift + p`，在弹出的菜单中搜索 `Markdown Preview Enhanced: Create TOC`，即可插入目录。

#### 注意

目录需要保存文件之后才能看到，所以需要先按下 `Ctrl + s` 进行保存，更多的细节可以参见插件的[文档](https://shd101wyy.github.io/markdown-preview-enhanced/#/zh-cn/toc)

---

原文中的分割线可以通过 Markdown 中的 `---` 来实现

---

```markdown
---

这是一段分割线

---
```

### 正文

正文写作就是正常的 Markdown 的写作，使用基础的 Markdown 语法即可。如果想要调整图片格式的，可以使用 html 语法，Markdown 兼容 html 语法，可以使用 css 格式实现很多效果。当然，如果你比较喜欢 Markdown 的简洁理念，这些就不在你的考虑范围之内了 >_<

### 徽章

#### 简单制作

原文中使用了徽章制作，这是基于 [shields.io](https://shields.io) 进行生成的。在官网的 Get Started 页面中，我们可以可以看见右侧有一个徽章制作栏：

<center>
    <img src="/img/shields.png" style="border-radius: 0.3125em; box-shadow: 0 2px 4px 0 "
    width="65%" alt="图片加载失败" />
    <br>
    shields.io Get Started 页面
</center>

在制作栏中可以生成静态徽章。在 badgeContent 中输入你想要的徽章名称、颜色即可。比如制作 GitHub 个人主页徽章，只需要输入

```txt
GitHub-hxzsty233-blue
```

就得到了一个徽章：`<img alt="Static Badge" src="https://img.shields.io/badge/GitHub-hxzsty233-blue" style="margin: 0 2px -4px 2px ">`

如果想要给徽章添加 logo，可以点击 `+ Show optional parameters`，如图

<center>
    <img src="/img/shields_hide.png" style="border-radius: 0.3125em; box-shadow: 0 2px 4px 0 "
    width="65%" alt="图片加载失败" />
    <br>
</center>

之后可以在下拉的窗口中找到 Logo 选项，填入你想要设置的 Logo 即可。比如我可以为之前的徽章添加 GitHub logo：`<img alt="Static Badge" src="https://img.shields.io/badge/GitHub-hxzsty233-blue?logo=github" style="margin: 0 2px -4px 2px ">`。当然，如果你填写 Java，那么你会发现 Java 的咖啡图标无法生成，这是因为 shields.io 的 Logo 生成基于 simple-icons 库，如果你想查找的 Logo 不在库内，那么自然无法生成。你可以在[这里](https://simpleicons.org/)查看图标有没有包含在库内。

#### 小技巧

如果你是直接复制 shields.io 给出的 Markdown 链接，那么你可能会看到这样的情况：![Static Badge](https://img.shields.io/badge/GitHub-hxzsty233-blue?logo=github)，徽章和行间正文不在一条水平线上，看起来歪歪扭扭。这可能是因为徽章是作为图像导入，它的外边距设置过大。解决办法是使用 html 标签导入，在 img 属性中添加 style，示例：

```html
<img alt="Static Badge" src="https://img.shields.io/badge/GitHub-hxzsty233-blue?logo=github" style="margin: 0 2px -4px 2px ">
```

这样得到的徽标就可以完美融入行间正文了。

## 导出 pdf 格式

Markdown 转 pdf 已经有成熟的工具，比如 pandoc, prince 等等，许多 Markdown 编辑器也都支持直接导出 pdf 文件。

但是这种直接导出有一个问题，就是导出的 pdf 会在一些地方插入大片空白，使得文章看起来不连贯。而且制作的徽章也会单独成行，不好看。

这里推荐使用网页的打印功能，即先转换成 html，再使用网页的 `打印` 生成 pdf。注意：使用打印时如果还是遇到格式错误，可以先 `Ctrl + A` 全部选中，之后再打印，这样可以和你看见的格式保持一致。打印的时候记得勾选 `更多`里的 `背景图形`选线，否则分割线可能无法显示。

# 使用 Markdown 写作个人简介

好的个人简介可以给导师留下深刻印象。如果你想让自己的个人简介变得炫酷一点，可以使用我上面提到的徽章制作技巧。让自己的技术栈看起来更炫酷！

# 写在最后

在写作 ospp 申请书的时候，我遇到了许多困惑。申请书的示例只有 pdf 的成品格式，缺少了很多写作的细节。我自己花了很多时间才弄明白示例是如何生产出来的，如果后来人看到我这篇文章，就可以节省很多不必要的时间，专心在项目的研究上。

我坚信，开源的核心就是分享。我所走过的弯路，别人不必再走一遍
