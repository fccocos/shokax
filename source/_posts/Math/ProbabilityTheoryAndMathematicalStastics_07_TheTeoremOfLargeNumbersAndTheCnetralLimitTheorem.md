---
title: 第七章 大数定律与中心极限定理
categories:
  - 数学
  - 概率论与数理统计
tag:
  - 数学
  - - 数学
    - 概率论与数理统计
math: true
sticky: true
abbrlink: 20f71bd7
date: 2023-08-28 16:18:08
---

{% markmap 750px %}

- 大数定律与中心极限定理
  - 依概率收敛
    - $\lim\limits_{n\to \infty}P\{|X_n-X|\ge \varepsilon\}=0$
    - $\lim\limits_{n\to \infty}P\{|X_n-X|<\varepsilon\}=1$
  - 大数定律
    - 切比雪夫大数定律：$\frac{1}{n}\sum\limits_{i=1}X_i\to \frac{1}{n}\sum\limits_{i=1}^nEX_i$
    - 伯努利大数定律：$\lim\limits_{n\to \infty}P\{|\frac{\mu_n}{n}-p|<\varepsilon\}=1$
    - 辛钦大数定律：$\lim\limits_{n\to\infty}P\{|\frac{1}{n}\sum\limits_{i=1}^nX_i-\mu|<\varepsilon\}=1$
    - 考结论：$\frac{1}{n}\sum\limits_{i=1}^nX_i\to E(\frac{1}{n}\sum\limits_{i=1}^nX_i)$
  - 中心极限定理
    - 列维—林德伯格定理：$\lim\limits_{n\to\infty}P\{\frac{\sum\limits_{i=1}^nX_i-n\mu}{\sqrt{n}\sigma}\le x\}=\frac{1}{\sqrt{2\pi}}\int_{-\infty}^xe^{-\frac{1}{2}t^2}dt=\Phi(x)$
    - 枥莫弗—拉普拉斯定理：$\lim\limits_{n\to\infty}P\{\frac{Y_n-np}{\sqrt{np(1-p)}}\le x\}=\frac{1}{\sqrt{2\pi}\int_{-\infty}^x}e^{-\frac{t^2}{2}}dt=\Phi(x)$
    - 考结论：$\lim\limits_{n\to \infty}P\{\frac{\sum\limits_{i=1}^nX_i-n\mu}{\sqrt{n}\sigma}\le x\}=\Phi(x)$


{% endmarkmap %}