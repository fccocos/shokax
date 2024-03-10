---
title: 第二章 一维随机变量及其分布
categories:
  - 数学
  - - 概率论与数理统计
tag:
  - 数学
  - - 数学
    - 概率论与数理统计
math: true
sticky: true
abbrlink: 20f71bd7
date: 2023-08-20 11:12:08
---

{% markmap 750px %}

- 一维随机变量及其分布
  - 判分布
    - 随机变量及其分布函数的定义
      - 随机变量
      - 分布函数
    - 判分布
      - 分布函数
        - 单调不减
        - 右连续
        - $F(-\infty)=0$
        - $F(+\infty)=1$
      - 概率分布(离散型): $p_i \ge 0, \sum\limits_i p_i=1$
      - 概率密度(连续型): $f(x)\ge 0, \int_{-\infty}^{+\infty}f(x)=1$
      - 反问题
        - $F(-\infty)=0$
        - $F(+\infty)=1$
        - $\sum\limits_i p_i =1$
        - $\int_{-\infty}^{+\infty}f(x)=1$
  - 求分布
    - 离散型分布
      - 0——1分布: $\begin{pmatrix}1&0\\p&1-p\end{pmatrix}$
      - 二项分布: $P\{X=k\}=C_n^kp^k(1-p)^{n-k}$
      - 几何分布: $P\{X=k\}=(1-p)^{k-1}p$
      - 超几何分布：$P\{X=k\}=\frac{C_M^kC_{N-M}^{n-k}}{C_n^N},\max\{0,n-N+M\}\le k \le \min\{n,M\}$
      - 泊松分布：$P\{X=k\}=\frac{\lambda^k}{k!}e^{-\lambda}$
    - 连续型
      - 均匀分布：$f(x)=\begin{cases}\frac{1}{b-a},&a\le x \le b,\\0,&others.\end{cases}$
      - 指数分布：$f(x)=\begin{cases}\lambda e^{-\lambda x},&x\ge 0,\\0,&others.\end{cases}$
      - 正态分布：$f(x)=\frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{x-u}{2\sigma^2}}$
  - 用分布
    - $X\sim F(x)$
      - $P\{x\le a\} = F(a)$
      - $P\{X<a\}=F(a-0)$
      - $P\{X=a\}=P\{X\le a\}-P\{X<a\}=F(a)-F(a-0)$
      - $P\{a<X<b\}=P\{X<b\}-P\{X\le a\}=F(b-0)-F(a)$
      - $P\{a\le X\le b\}=P\{X\le b\}-P\{X<a\}=F(b)-F(a-0)$
    - $X\sim p_i$: $P\{X\in I\}=\sum\limits_{x_i\in I}P\{X=x_i\}$
    - $X\sim f(x)$: $P\{X\in I\}=\int_I f(x)dx$
    - 反问题：已知概率求参数。  

{% endmarkmap %}