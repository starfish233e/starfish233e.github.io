---
title: Frullani 积分
date: 2024-11-29 11:55:00
categories: 数学
tags: 数学分析
math: true
---

## 引入

昨天做题的时候遇到一个问题：求拉普拉斯变换

$$
\mathcal{L}{\left[\frac{e^{-t}-e^{-3t}}{t}\right]}
$$

我们知道，$\dfrac{1}{t}$ 是不可积的，它不满足做 Laplace 变换的条件。那么这个变换如何进行呢？在群友的点拨下，我发现这个积分变换

$$
\int_{0}^{+\infty}\frac{e^{-t}-e^{-3t}}{t} \cdot e^{-st}\mathrm{d}t
$$

其实是 Frullani 积分：

$$
\text{若}\lim_{x \to +\infty}f(x) = k, \, 则有 \int_{0}^{+\infty}\frac{f(ax)-f(bx)}{x}\mathrm{d}x = \left[f(0)-k\right]\ln\frac{b}{a}
$$

## Frullani 积分

证明：

$$
\begin{aligned}
\int_{0}^{+\infty}\frac{f(ax)-f(bx)}{x}\mathrm{d}x 
&= \lim_{\substack{m \to 0 \\ M \to +\infty}}\int_{m}^{M}\frac{f(ax)-f(bx)}{x}\mathrm{d}x \\
&= \lim_{\substack{m \to 0 \\ M \to +\infty}}\int_{am}^{aM}\frac{f(t)}{t}\mathrm{d}t - \lim_{\substack{m \to 0 \\ M \to +\infty}}\int_{bm}^{bM}\frac{f(t)}{t}\mathrm{d}t \\
&= \lim_{\substack{m \to 0 \\ M \to +\infty}}\int_{am}^{bm}\frac{f(t)}{t}\mathrm{d}t + \lim_{\substack{m \to 0 \\ M \to +\infty}}\int_{bm}^{aM}\frac{f(t)}{t}\mathrm{d}t - \lim_{\substack{m \to 0 \\ M \to +\infty}}\int_{bm}^{aM}\frac{f(t)}{t}\mathrm{d}t \\ 
&\, -\lim_{\substack{m \to 0 \\ M \to +\infty}}\int_{aM}^{bM}\frac{f(t)}{t}\mathrm{d}t \\
&=\lim_{\substack{m \to 0 \\ M \to +\infty}}\int_{am}^{bm}\frac{f(t)}{t}\mathrm{d}t -\lim_{\substack{m \to 0 \\ M \to +\infty}}\int_{aM}^{bM}\frac{f(t)}{t}\mathrm{d}t \\
&= \lim_{\substack{m \to 0 \\ M \to +\infty}}f(\xi_{1})\int_{am}^{bm}\frac{1}{t}\mathrm{d}t - \lim_{\substack{m \to 0 \\ M \to +\infty}}f(\xi_{2})\int_{aM}^{bM}\frac{1}{t}\mathrm{d}t \\
&= \left[f(0)-k\right]\ln\frac{b}{a}
\end{aligned}
$$

其他证明可见[维基百科](https://en.wikipedia.org/wiki/Frullani_integral)(需要用到积分换序)

## 问题解决

$$
\int_{0}^{+\infty}\frac{e^{-t}-e^{-3t}}{t} \cdot e^{-st}\mathrm{d}t = (1-0)\ln\frac{s+3}{s+1} = \ln\frac{s+3}{s+1}
$$


