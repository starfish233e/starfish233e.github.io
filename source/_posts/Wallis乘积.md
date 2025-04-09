---
title: Wallis乘积
date: 2024-07-11 15:22:49
tags: 数学分析
categories: 数学
math: true
---

## 1.Wallis 公式

求证：

$$
\int_{0}^{\frac{\pi}{2}}\sin^{n}x\mathrm{d}x = \int_{0}^{\frac{\pi}{2}}\cos^{n}x\mathrm{d}x = 
\begin{cases}
    \frac{(n-1)!!}{n!!}, \quad \, \, \, n  \, \text{为奇数}, \\
    \frac{\pi}{2} \cdot \frac{(n-1)!!}{n!!}, \, n \, \text{为偶数}, 
\end{cases}
$$

证明：

$$
\text{由} \int_{0}^{\frac{\pi}{2}}\sin^n{x}\mathrm{d}x = \int_{\frac{pi}{2}}^{\pi}(-\cos x)^n \mathrm{d}x = \int_{0}^{\frac{\pi}{2}} \cos^n x \mathrm{d}x \, \text{可知只需证} \sin x \text{一种即可}
$$

设

$$ 
\int_{0}^{\frac{\pi}{2}}\sin^n{x}\mathrm{d}x = I_{n}
$$ 

则有

$$
\begin{aligned}
    I_{n} &= \int_{0}^{\frac{\pi}{2}}\sin^{n-1}{x} \sin x\mathrm{d}x = -\int_{0}^{\frac{\pi}{2}}\sin^{n-1}{x}\mathrm{d}(\cos x) \\
    &= - \cos x \sin^{n-1}x |_{0}^{\frac{\pi}{2}} + \int_{0}^{\frac{\pi}{2}} \sin^{n-2}x \cdot\cos^2x \mathrm{d}x \\
    &= (n-1)\left[I_{n-2} - I_{n}\right]
\end{aligned}
$$

即得到了递推式:

$$
I_{n} = \frac{n-1}{n}I_{n-2}
$$

结合 n=0 以及 n=1 时的情况可知

$$
\begin{cases}
    I_{2n} = \frac{\pi}{2} \cdot \prod_{m=1}^{n} \frac{2m-1}{2m}, \\
    I_{2n+1} = \prod_{m=1}^{n} \frac{2m}{2m+1},
\end{cases}
$$

## 2.Wallis乘积

由上式可以知道 

$$
\frac{\pi}{2} = \frac{\int_{0}^{\frac{\pi}{2}}\sin^{2n}x\mathrm{d}x}{\int_{0}^{\frac{\pi}{2}}\sin^{2n+1}x\mathrm{d}x} \cdot \prod_{m=1}^{n}\frac{2m}{2m-1} \cdot \frac{2m}{2m+1}
$$

下面来求极限

$$
\frac{\int_{0}^{\frac{\pi}{2}}\sin^{2n}x\mathrm{d}x}{\int_{0}^{\frac{\pi}{2}}\sin^{2n+1}x\mathrm{d}x}
$$

$$
1 = \frac{\int_{0}^{\frac{\pi}{2}}\sin^{2n+1}x\mathrm{d}x}{\int_{0}^{\frac{\pi}{2}}\sin^{2n+1}x\mathrm{d}x} < \frac{\int_{0}^{\frac{\pi}{2}}\sin^{2n}x\mathrm{d}x}{\int_{0}^{\frac{\pi}{2}}\sin^{2n+1}x\mathrm{d}x} < \frac{\int_{0}^{\frac{\pi}{2}}\sin^{2n-1}x\mathrm{d}x}{\int_{0}^{\frac{\pi}{2}}\sin^{2n+1}x\mathrm{d}x} = \frac{2n+1}{2n}
$$

根据夹逼法则可以得到上式极限为一，那么

$$
\frac{\pi}{2} = \lim_{n \to \infty}\prod_{m=1}^{n}\frac{2m}{2m-1} \cdot \frac{2m}{2m+1} = \lim_{n \to \infty} \left[\frac{(2n)!!}{(2n-1)!!}\right]^2 \cdot \frac{1}{2n+1}
$$

## 3.例题

题目：
$$
\text{设} \, a_{n} = \int_{0}^{\frac{\pi}{2}}\cos^{n+1}x \mathrm{d}x， \text{求} \lim_{n \to \infty} n a_{n}^2
$$

i. n 为奇数

$$
a_{n} = \int_{0}^{\frac{\pi}{2}}\cos^{n+1}x \mathrm{d}x = \frac{(2m-1)!!}{(2m)!!} \cdot \frac{\pi}{2} \\
\lim_{n \to \infty} n a_{n}^2 = \frac{\pi}{4}
$$

$ii. n 为偶数$

$$
\lim_{n \to \infty} n a_{n}^2 = \frac{1}{\pi}
$$
