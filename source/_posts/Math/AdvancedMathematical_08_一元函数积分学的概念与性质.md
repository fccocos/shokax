---
title: 第八章 一元函数积分学的概念与性质
math: true
sticky: true
date: 2023-09-1 17:01:12
---

{% markmap 750px %}

- 一元函数积分学的概念与性质
  - 祖孙三代的奇偶性、周期性：$\int_a^xf(t)dt,f(x),f^{'}(x)$的7条关系
  - 积分比大小
    - 用公式或几何意义
    - 用保号性
      - 看正负
      - 作差
  
  - 定积分定义
    - 基本形（能凑成$\frac{i}{n}$）
      - $\lim\limits_{n\to\infty}\sum\limits_{i=1}^nf(0+\frac{1-0}{n}i)\frac{1-0}{n}=\int_0^1f(x)dx$
      - $\lim\limits_{n\to\infty}\sum\limits_{i=0}^{n-1}f(0+\frac{1-0}{n}i)\frac{1-0}{n}=\int_0^1f(x)dx$
  
    - 放缩形(凑不成$\frac{i}{n}$)
      - 夹逼定理
      - 放缩后再凑$\frac{i}{n}$
      - 变量形: $\lim\limits_{n\to\infty}\sum\limits_{i=1}^nf(0+\frac{x-0}{n}i)\frac{x-0}{n}=\int_0^xf(t)dt$
  
  - 反常积分的判敛
    - 概念
    - 判别
  

{% endmarkmap %}