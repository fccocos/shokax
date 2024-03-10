---
title: 第九章 参数估计与假设检验
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
date: 2023-08-28 21:18:08
---

{% markmap 750px %}

- 参数估计与假设检验
  - 点估计和评价标准
    - 距估计
      - 一个参数
        - 用一阶矩建立方程，令$\overline{X}=EX$
        - 用二阶距建立方程，令$\frac{1}{n}\sum\limits_{i=1}^nX_i^2=E(X^2)$
  
      - 两个参数：用一阶距与二阶矩建立两个方程
  
    - 最大似然估计
      - 写似然估计：$L(x_i;\theta)=$
        - $\prod\limits_i^np(x_i;\theta)$(离散型总体X取$x_i$的概率)
        - $\prod\limits_{i=1}^nf(x_i;\theta)$(连续型总体X取$x_i$的联合概率密度)
  
      - 求参数
        - 有驻点，令$\frac{dL}{d\theta}=0$或$\frac{d\ln L}{d\theta}=0$
        - 无驻点（单调），用定义求$\widehat{\theta},\widehat{\theta}$不唯一
  
      - 不变性原则
  
    - 估计量的评价
      - 无偏性：$E\widehat{\theta}=\theta$
      - 有效性：$D\widehat{\theta_1}<D\widehat{\theta_2},$称$\widehat{\theta_1}$比$\widehat{\theta_2}$有效
      - 一致性（相合性）
        - $\lim\limits_{n\to\infty}P\{|\widehat{\theta}-\theta|\ge \varepsilon\}=0$
        - $\lim\limits_{n\to\infty}P\{|\widehat{\theta}-\theta|<\varepsilon\}=1$
  
    - 估计量的数字特征
      - 求$E\widehat{\theta}$
      - 求$D\widehat{\theta}$
      - 验证是否有$\widehat{\theta}\to\theta$
  
  - 区间估计与假设检验
    - 区间估计
      - 概念
      - 单个正态总体均值和方差的置信区间
  
    - 假设检验
      - 概念
      - 原假设与备择假设
      - 小概率原理与显著性水平
      - 正态总体的六大检验及拒绝域
  
    - 两类错误
      - 第一类错误（“弃真”）
      - 第二类错误（“取伪”）
  


{% endmarkmap %}