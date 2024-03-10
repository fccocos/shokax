---
title: 第八章 统计量及其分布
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

- 统计量及其分布
  - 统计量
    - 样本均值：$\overline{X}=\frac{1}{n}\sum\limits_{i=1}^nX_i$
    - 样本方差：$S^2=\frac{1}{n-1}\sum\limits_{i=1}^n(X_i-\overline{X})^2=\frac{1}{n-1}(\sum\limits_{i=1}^nX_i^2-n\overline{X}^2)$
    - 样本标准差：$S=\sqrt{\frac{1}{n-1}\sum\limits_{i=1}^n(X_i-\overline{X})^2}$
    - 样本k阶原点距：$A_k=\frac{1}{n}\sum\limits_{i=1}^nX_i^k(k=1,2,\cdots)$
    - 样本k阶中心距：$B_k=\frac{1}{n}\sum\limits_{i=1}^n(X_i-\overline{X})^k(k=2,3,\cdots)$
    - 顺序统计量
      - $X_{(1)}=\min\{X_1,X_2,\cdots,X_n\}$
      - $X_{(n)}=\max\{X_1,X_2,\cdots,X_n\}$
  - 统计量的分布
    - 正态分布：$X\sim N(0,1),P\{X>\mu_\alpha\}=\alpha(0<\alpha <1)$
    - $\varkappa^2分布$
      - $X_1,X_2,\cdots,X_n$独立同服从$N(0,1)$,则$X=\sum\limits_{i=1}^nX_i^2\sim \varkappa^2(n)$
      - $EX=n,DX=2n$
    - t分布
      - $X\sim N(0,1),Y\sim \varkappa^2(n),X,Y$独立，$t=\frac{X}{\sqrt{Y/n}}\sim t(n)$
      - $t_{1-\alpha}(n)=-t_{\alpha}(n)$
    - F分布
      - $X\sim\varkappa^2(n_1),Y\sim\varkappa^2(n_2),X,Y$独立，$F=\frac{X/n_1}{Y/n_2}\sim F(n_1,n_2)$
      - $\frac{1}{F}\sim F(n_1,n_2), F_{1-\alpha}(n_1,n_2)=\frac{1}{F_\alpha(n_2,n_1)}$
  - 正态总体下的常用结论
    - $\overline{X}\sim N(\mu,\frac{\sigma^2}{n}),$即$\frac{\overline{X}-\mu}{\frac{\sigma}{\sqrt{n}}}=\frac{\sqrt{n}(\overline{X}-\mu)}{\sigma}\sim N(0,1)$
    - $\frac{1}{\sigma^2}\sum\limits_{i=1}(X_i-\mu)^2\sim\varkappa^2(n)$
    - $\frac{(n-1)S^2}{\sigma^2}=\sum\limits_{i=1}^n(\frac{X_i-\overline{X}}{\sigma})\sim \varkappa^2(n-1)$
    - $\frac{n(\overline{X}-\mu)^2}{S^2}\sim F(1,n-1)$


{% endmarkmap %}