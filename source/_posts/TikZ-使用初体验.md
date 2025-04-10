---
title: TikZ 使用初体验
date: 2024-11-19 20:46:32
tags: LaTeX
categories: 随笔
math: true
---

## 画图是使用 $\LaTeX$ 的痛点

如何精确地画图，是 $\LaTeX$ 中一大难题。数学绘图软件如 **Mathmetica, Matlab, Geogebra**等都使用自己的编程语言，以及相应的绘图库（library）进行支持，而 $\LaTeX$ 中使用的编程系统就是 TikZ, 一种绘图宏包。使用编程语言绘制平面几何图形从来不是一件简单的事情，甚至可以说费时费力有些得不偿失，但是从代码的统一性上来说，用编程语言画图可以省去切换软件和形象思维的麻烦，也能够做到更精确的绘制。

## 我和 TikZ 的缘分

TikZ 的大名在我已是久仰，刚刚接触 $\LaTeX$ 的时候, 我就已经听说了 TikZ。作为 $\TeX$ 排版系统中最负盛名的绘图宏包，TikZ 勾起了我内心深处的渴望。然而，作为 $\TeX$ 的一个组成部分，TikZ 也继承了它的繁杂庞大，学习成本可谓非常高昂。仅仅是参考手册就长达数千页，浩如烟海的文本简直令人望而却步。于是我在很长一段时间内都没有想过去学习它，遇到需要绘图的场景也选择其他绘图工具，直到最近我偶然遇到了一道数学问题。这道问题以高中平面几何为背景，需要绘制的图形非常简单，而 $\TeX$ 文档对于插入图片的支持又是令人印象深刻的糟糕，这使得我决定使用 TikZ 来画图。

学习 TikZ 的过程比想象中要轻松，虽然遇到了些许问题卡壳了许久，但是仍然能通过查找资料和询问网友解决。最终看到成品的 $\LaTeX$ 文档，对我这两天以来反复的尝试和查资料是莫大的慰藉。

附上我使用 TikZ 制作的[文档](/downloads/盒友的小难题.pdf)：

![第一页](/img/盒友的小难题_页面_1.png)
![第二页](/img/盒友的小难题_页面_2.png)
![第三页](/img/盒友的小难题_页面_3.png)


