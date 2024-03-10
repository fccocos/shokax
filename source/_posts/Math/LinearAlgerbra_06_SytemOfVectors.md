---
title: 第六章 向量组
categories:
  - 数学
  - 线性代数
tag:
  - 数学
  - - 数学
    - 线性代数
math: true
sticky: true
abbrlink: 1c2ce631
date: 2023-08-27 09:42:22
---

{% markmap 750px %}

- 向量组
  
  - 定义与定理
    - 定义
      - n维向量
      - 线性组合
      - 线性表示
      - 线性相关
      - 线性无关
  
    - 判别线性相关的八大定理
      - 定理1
      - 定理2
      - 定理3
      - 定理4
      - 定理5
      - 定理6
      - 定理7
      - 定理8
  - 具体型向量关系
    - $\beta$与$\alpha_1,\alpha_2,\cdots,\alpha_n$
      - 建立方程组：$[\alpha_1,\alpha_2,\cdots,\alpha_n]\begin{bmatrix}x_1\\x_2\\\vdots\\x_n\end{bmatrix}=\beta$
      - 化为阶梯：$[A\vdots \beta]=[\alpha_1,\alpha_2,\cdots,\alpha_n\vdots \beta]$经过初等行变换变成阶梯矩阵
      - 讨论
        - $r(A)\ne r([A\vdots b])\Leftrightarrow$无解$\Leftrightarrow$不能表示
        - $r(A)=r([A\vdots b])=n\Leftrightarrow$有唯一解$\Leftrightarrow$唯一一种表示
        - $r(A)=r([A\vdots b])<n\Leftrightarrow$有无穷多解$\Leftrightarrow$无穷多种表示
    - $\alpha_1,\alpha_2,\cdots,\alpha_n$
      - 向量个数大于维数：必线性关系
      - 向量个数等于维数
        - $|\alpha_1,\alpha_2,\cdots,\alpha_n|=0\Leftrightarrow$线性相关
        - $|\alpha_1,\alpha_2,\cdots,\alpha_n|\ne 0\Leftrightarrow$线性无关
      - 向量个数小于维数
        - $r(A)<n\Leftrightarrow$线性相关
        - $r(A)=n\Leftrightarrow$线性无关
        - 若线性相关，问 $\alpha_s$与$\alpha_1,\cdots,\alpha_{s-1},\alpha_{s+1},\cdots,\alpha_n$的表示关系
    - 求极大线性无关组
      - 定义
        - 线性无关
        - 向量组中任意向量均可由它线性表出
      - 求法
        - 构造$A=[\alpha_1,\alpha_2,\cdots,\alpha_n]$
        - A经过初等行变换变成B（阶梯形）
        - 算出台阶数r，按列找出一个秩为r的子矩阵即可
  - 抽象型向量关系
    - 定义法
      - 写定义式$k_1\alpha_1+k_1\alpha_2+\cdots+k_n\alpha_n=0$
      - 考察$k_1=k_2=\cdots=k_n=0$是否成立
  
    - 用秩
  
  - 向量组等价：$I\cong II\Leftrightarrow r(I)=r(II),$且可单方向表示$\Leftrightarrow r(I)=r(II)=r(I,II)$
  - 向量空间
    - 概念
      - 基
      - 维数
      - 坐标
  
    - 过渡矩阵：$[\eta_1,\eta_2,\cdots,\eta_n]=[\xi_1,\xi_2,\cdots,\xi_n]C$
    - 坐标转换: $\alpha=[\xi_1,\xi_2,\cdots,\xi_n]x=[\eta_1,\eta_2,\cdots,\eta_n]y=[\xi_1,\xi_2,\cdots,\xi_n]Cy$
  

{% endmarkmap %}