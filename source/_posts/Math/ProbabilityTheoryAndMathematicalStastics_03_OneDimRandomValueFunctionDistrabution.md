---
title: 第三章 一维随机变量函数分布
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
date: 2023-08-28 11:12:08
---

{% markmap 750px %}

- 一维随机变量函数的分布
  - 离散型$\to$离散型：$p_i=P\{X=x_i\},Y=g(X),Y\sim\begin{pmatrix}g(x_1)&g(x_2)&\cdots\\p_1&p_2&\cdots\end{pmatrix}$
  - 连续型$\to$连续型 (或混合型)：
    - 分布函数法: $F_Y(y)=P\{Y\le y\}=P\{g(x)\le y\}=\int_{g(x)\le y}f_X(x)dx$
    - 公式法：$f_Y(y)=\begin{cases}f_x[h(y)]\cdot |h^{'}(y)|,&\alpha<y<\beta\\0,&其他 \end{cases}$
  
  - 连续型$\to$离散型: $X\sim f_X(x), Y=g(X)$离散，确定Y的可能取值a，计算$P\{Y=a\}$,求Y的概率分布
  

{% endmarkmap %}