---
title: 第七章 特征值与特征向量
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
date: 2023-08-27 10:13:22
---

{% markmap 750px %}

- 特征值与特征向量
  - 特征值与特征向量的定义：$A\xi=\lambda\xi,\xi\ne 0$
  - 用特征值命题
    - $\lambda_0$是A的特征值$\Leftrightarrow|\lambda_0E-A|=0;\lambda_0$不是A的特征值$\Leftrightarrow|\lambda_0E-A|\ne 0$
    - $\lambda_1,\lambda_2,\cdots,\lambda_n$是A的n个特征值，则$\begin{cases}|A|=\lambda_1\lambda_2\cdots\lambda_n\\tr(A)=\lambda_1+\lambda_2+\cdots+\lambda_n\end{cases}$
    - 重要结论
      - 记住表格
      - 虽然$A^T$的特质值与A相同，但特征向量不再是$\xi$,要单独计算才能得出
      - $f(x)$为多项式，若矩阵A满足$f(A)=O,\lambda$是A的任一特征值，则$\lambda$满足$f(\lambda)=0$
  - 用特征向量命题
    - $\xi(\ne 0)$是A的属于$\lambda_0$的特征向量$\Leftrightarrow$$\xi$是$(\lambda_0E-A)x=0$的非零解
    - 重要结论
      - k重特征值$\lambda$至多只有k个线性无关的特征向量
      - $\xi_1,\xi_2$是A的属于不同特征值$\lambda_1,\lambda_2$的特征向量，则$\xi_1,\xi_2$线性无关
      - $\xi_1,\xi_2$是A的属于同一特征值$\lambda$的特征向量，则非零向量$k_1\xi_1+k_2\xi_2$仍是A的属于特征值$\lambda$的特征向量
      - $\xi_1,\xi_2$是A的属于不同特征值$\lambda_1,\lambda_2$的特征向量，则当$k_1\ne 0,k_2\ne 0$时，$k_1\xi_1+k_2\xi_2$不是A的任何特征值的特征向量
      - n阶矩阵A，B满足$AB=BA$，且A有n个互不相同的特征值，则A的特征向量都是B的特征向量
  - 用矩阵方程命题
    - $AB=0\Rightarrow A[\beta_1,\beta_2,\cdots,\beta_n]=[0,0,\cdots,0],$即$A\beta_i=0\beta_i(i=1,2,\cdots,n),$若$\beta_i$均为非零向量，则$\beta_i$为A的属于$\lambda=0$的特征向量
    - $AB=C\Rightarrow A[\beta_1,\beta_2,\cdots,\beta_n]=[\gamma_1,\gamma_2,\cdots,\gamma_n]=[\lambda_1\beta_1,\lambda_2\beta_2,\cdots,\lambda_n\beta_n],$即$A\beta_i=\lambda_i\beta_i(i=1,2,\cdots,n),$其中$\gamma_i=\lambda_i\beta_i,\beta_i$为非零列向量，则$\beta_i$ 为A的属于$\lambda_i$的特征向量
    - $AP=PB,P$可逆$\Rightarrow P^{-1}AP=B\Rightarrow A\sim B\Rightarrow \lambda_A=\lambda_B$
    - A的每行元素之和均等于k$\Rightarrow A\begin{bmatrix}1\\1\\\vdots\\1\end{bmatrix}=k\begin{bmatrix}1\\1\\\vdots\\1\end{bmatrix}\Rightarrow k$是特征值，$\begin{bmatrix}1\\1\\\vdots\\1\end{bmatrix}$是A的属于k的特征向量

{% endmarkmap %}