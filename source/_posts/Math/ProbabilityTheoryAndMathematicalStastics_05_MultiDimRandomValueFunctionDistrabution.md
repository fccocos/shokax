---
title: 第五章 多维随机变量函数的分布
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

- 多维随机变量函数的分布
  - 多维$\to$一维
  
    - （离散型，离散型）$\to$离散型
      - $(X,Y)\sim p_{ij},Z=g(X,y)\Rightarrow$Z的分布律
  
      - $X\sim p_k,Y\sim q_k,\begin{cases}Z=X+y\\Z=XY\\Z=\max\{X,Y\}\\Z=\min\{X,Y\}\end{cases}$ Z的分布律
  
    - （连续型，连续型）$\to$连续型
      - 分布函数法: $F_Z(z)=P\{g(X,Y)\le Z\}=\iint\limits_{g(x,y)\le z}f(x,y)dxdy$
  
      - 卷积公式法
        - $Z=X+Y\Rightarrow f_Z(z)=\int_{-\infty}^{+\infty}f(x,z-x)dx=\int_{-\infty}^{+\infty}f(z-y,y)dy=\int_{-\infty}^{+\infty}f_X(x)f_Y(z-x)dx=\int_{-\infty}^{+\infty}f_X(z-y)f_Y(y)dy$
  
        - $Z=X-Y\Rightarrow f_Z(z)=\int_{-\infty}^{+\infty}f(x,x-z)dx=\int_{-\infty}^{+\infty}f(y+z,y)dy=\int_{-\infty}^{+\infty}f_X(x)f_Y(x-z)dx=\int_{-\infty}^{+\infty}f_X(y+z)f_Y(y)dy$
  
        - $Z=XY\Rightarrow f_Z(z)=\int_{-\infty}^{+\infty}\frac{1}{|x|}f(x,\frac{z}{x})dx=\int_{-\infty}^{+\infty}\frac{1}{|y|}f(\frac{z}{y},y)dy=\int_{-\infty}^{+\infty}\frac{1}{|y|}f_X(\frac{z}{y})f_Y(y)dy$
  
        - $Z=\frac{X}{Y}\Rightarrow f_Z(z)=\int_{-\infty}^{+\infty}|y|f(yz,y)dy=\int_{-\infty}^{+\infty}|y|f_X(yz)f_Y(y)dy$
  
      - 最值分布
        - $P\{\max\{X,Y\}\le z\}=P\{X\le z, Y\le z\}=F(z,z)$
  
        - $P\{\min\{X,Y\}\le z\}=F_X(z)+F_Y(z)-F(z,z)$
  
    - （离散型，连续型）$\to$连续型：$X\sim p_i,Y\sim f_Y(y),Z=g(X,Y)$
  
  - 一维$\to$多维
    - 离散型$\to$（离散型，离散型）：$X\sim p_i,\begin{cases}U=g(X),\\V=h(X)\end{cases}\Rightarrow(U,V)\sim q_{ij}$
    - 连续型$\to$（离散型，离散型）：$X\sim f(x),\begin{cases}U=g(x),\\V=h(x)\end{cases}\Rightarrow(U,V)\sim p_{ij}$
  
  - 多维$\to$多维
    - （离散型，离散型）$\to$（离散型，离散型）：$(X,Y)\sim p_{ij},\begin{cases}U=g(X,Y),\\V=h(X)\end{cases}\Rightarrow (U,V)\sim q_{ij}$
    - （连续型，连续型）$\to$（离散型，离散型）：$(X,Y)\sim f(x,y),\begin{cases}U=g(X,Y),\\V=h(X,Y)\end{cases}\Rightarrow (U,V)\sim p_{ij}$
    - （离散型，连续型）$\to$（离散型，离散型）：$X\sim p_i,Y\sim f_Y(y),\begin{cases}U=g(X,Y),\\V=h(X,Y)\end{cases}\Rightarrow (U,V)\sim q_{ij}$
  

{% endmarkmap %}