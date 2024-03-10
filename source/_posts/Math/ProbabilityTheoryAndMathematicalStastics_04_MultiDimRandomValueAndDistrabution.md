---
title: 第四章 多维随机变量及其分布
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

- 多维随机变量及其分布
  - 判分布
    - $F(x,y)是联合分布函数的充要条件$
      - 单调性：单调不减
      - 右连续性：$\begin{cases}\lim\limits_{x\to x_0^+}F(x,y)=F(x_0+0,y)=F(x_0,y)\\\lim\limits_{y\to y_0^+}F(x,y)=F(x,y_0+0)=F(x,y_0)\end{cases}$
      - 有界性: $0\le F(x,y)\le 1$
      - 非负性: $P\{x_1\le X\le x_2,y_1\le Y\le y_2\}\ge 0$
  
    - $\{p_{ij}\}$是联合分布律的充要条件: $p_{ij}\ge0$且$\sum\limits_{j=1}\sum\limits_{i=1}p_{ij}=1$
    - 反问题：$\begin{cases}F(-\infty,y)=0,F(x,-\infty)=0\\F(-\infty,-\infty)=0,F(+\infty,+\infty)=1\\\sum\limits_j\sum\limits_ip_{ij}=1,\int_{-\infty}^{+\infty}\int_{-\infty}^{+\infty}f(x,y)dxdy=1\end{cases}$
  
  - 求分布
    - 求联合分布
      - 求$F(x,y)$
        - $(X,Y)\sim p_{ij}$：$F(x,y)=P\{X\le x,Y\le y\}=\sum\limits_{x_i\le x,y_i\le y}p_{ij}$
        - $(X,Y)\sim f(x,y)$：$F(x,y)=P\{X\le x,Y\le y\}=\int_{-\infty}^xdu\int_{-\infty}^yf(u,v)dv$
  
      - 求$p_{ij}$（常与求$P(A)$结合）
      - 求$f(x,y)$
        - 二维均匀分布：$f(x,y)=\begin{cases}\frac{1}{S_D},&(x,y)\in D,\\0,&others,\end{cases}S_D$为区域D的面积
        - 二维正态分布: $f(x,y)=\frac{1}{2\pi\sigma_1\sigma_2\sqrt{1-\rho}}\exp\{-\frac{1}{2(1-\rho^2)}[(\frac{x-\mu_1}{\sigma_1})^2-2\rho(\frac{x-\mu_1}{\sigma_1})(\frac{x-\mu_2}{\sigma_2})+(\frac{y-\mu_2}{\sigma_2})^2]\},\mu_1\in R,\mu_2\in R,\sigma_1>0,\sigma_2>0,-1<\rho <1$
  
    - 求边缘分布
      - 求$F_X(x),F_Y(y)$
        - $F_X(x)=F(x,+\infty)$
        - $F_Y(y)=F(+\infty,y)$
  
      - 求$p_{i\cdot},p_{\cdot j}$
        - $p_{i\cdot}=\sum\limits_jp_{ij}$
        - $p_{\cdot j}=\sum\limits_i p_{ij}$
  
      - 求$f_X(x),f_Y(y)$
        - $f_X(x)=\int_{-\infty}^{+\infty}f(x,y)dy$
        - $f_Y(y)=\int_{-\infty}^{+\infty}f(x,y)dx$
  
    - 求条件分布
      - 求$P\{Y=y_j|X=x_i\},P\{X=x_i|Y=y_i\}$
        - $P\{Y=y_j|X=x_i\}=\frac{P\{X=x_i,Y=y_i\}}{P\{X=x_i\}}=\frac{p_{ij}}{p_{i\cdot}}$
        - $P\{X=x_i|Y=y_j\}=\frac{P\{X=x_i,Y=y_j\}}{P\{Y=y_j\}}=\frac{p_{ij}}{p_{\cdot j}}$
  
    - 判独立
      - 对任意$x,y,F(x,y)=F_X(x)\cdot F_Y(y)$
      - 对任意$i,j,p_{ij}=p_{i\cdot}p_{\cdot j}$
      - 联合分布律的每行元素对应成比例
      - 对任意$x,y,f(x,y)=f_X(x)f_Y(y)$
      - 若$f(x,y)$的非零区域是矩形，且$f(x,y)$能分解成仅含$x,y$的两个一元函数的乘积，则X与Y独立
      - 若$X_1,X_2,\cdots,X_n$相互独立，则其任意k个随机变量也相互独立，且其函数$g_1(X_1),g_2(X_2),\cdots,g_n(X_n)$也相互独立
  
  - 用分布
    - $(X,Y)\sim p_{ij},$则$P\{(X,Y)\in D\}=\sum\limits_{(x_i,y_j)\in D}p_{ij}$
    - $(X,Y)\sim f(x,y),$则$P\{(X,Y)\in D\}=\iint\limits_Df(x,y)dxdy$
    - $(X,Y)$为混合型，则用全概率公式
    - 反问题：已知概率反求参数
  

{% endmarkmap %}