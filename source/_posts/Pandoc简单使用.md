---

title: Pandoc简单使用
date: 2024-05-30 13:16:13
tags: 
- Pandoc
- 文档转换
categories: 技术

---
# Pandoc简单使用

## 1.什么是 Pandoc ?

### 1.简介

Pandoc 是一个基于 `GPL` 协议开源的免费命令行软件，由加州大学伯克利分校哲学系教授 John MacFarlane 使用 `Haskell` 语言开发，目前另一位核心开发者是来自德国的 Albert Krewinkel。截止 2022 年 12 月 10 日，Pandoc 的 GitHub 仓库拥有超过 27,000 个 Star，3,000 次 Fork。

### 2.下载

#### 1.Windows

可以使用官方的[下载程序](https://github.com/jgm/pandoc/releases/latest)，或者在 `PowerShell` 中运行如下命令：

```powershell
winget install --source winget --exact --id JohnMacFarlane.Pandoc
```

#### 2.Liunx or MacOS

参见[官方文档](https://pandoc.org/installing.html)

### 3.功能——文本转换的“瑞士军刀”

Pandoc 可以将 markdown 文本转换成 docx, pdf 等不同格式，一个简单的命令示范如下：

```shell
pandoc test_markdown.md -o test_docx.docx
```

其中，`pandoc` 命令启用 `pandoc` 命令行工具，`-o` 是选项 `--output` 的简写，可以转换文档格式。

转换生成的 `test_docx.docx` 文件将会放置在工作目录下。注意，`pandoc` 生成的 `.docx` 文件将会丢失原文件中的超链接，因此对于纯文本文件比较适用。

Pandoc 也可以将 markdown 转换成 pdf 格式，但是需要用户提供 latex 引擎。一个理想的引擎是 xelatex ，对于中文的支持更好，可以通过安装 TexLive 获得。一个使用 xelatex 引擎进行转换的例子如下：

```shell
pandoc test_markdown.md -o test_pdf.pdf --pdf-engine=xelatex
```

由于系统字体不同，pandoc 可能会报错，需要装对于中文支持更好的字体。

Pandoc 也提供了自定义的选项，用户可以自建模板对 pdf 进行格式化，比如使用 `eisvogel` 模板：

```shell
pandoc test_markdown.md -o test_pdf.pdf --pdf-engine=xelatex -template=template/eisvogel.latex
```

这里将模板存放在工作目录中的 `template` 文件夹中，执行命令就可以看到输出的 pdf 文件了。

## 2.Pandoc扩展知识

### [Pandoc 官方文档](https://pandoc.org/getting-started.html)

### [Pandoc 从入门到精通|少数派](https://sspai.com/post/77206)

### [从 Markdown 到 Pandoc](https://sspai.com/post/64842)
