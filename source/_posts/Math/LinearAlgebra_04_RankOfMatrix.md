---
title: 第四章 矩阵的秩
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
date: 2023-08-27 08:44:22
---

{% markmap 750px %}

- 矩阵的秩
  - 定义：A中最大的不为零的子式的阶数称为矩阵A的秩
  - 公式：
    - $0\le r(A_{m\times n})\le\min\{n,m\}$
    - $r(kA)=r(A)(k\ne 0)$
    - $r(A)=r(PA)=r(AQ)=r(PAQ)$(P,Q为可逆矩阵)
    - 设A是$m\times n$矩阵，B是$n\times s$矩阵，若$r(A)=n$(列满秩)，则$r(AB)=r(B);$若$r(B)=n$（行满秩），则$r(AB)=r(A)$
    - $r(AB)\le \min\{r(A),r(B)\}$
    - $r(A+B)\le r([A,B])\le r(A)+r(B)$
    - $r(\begin{bmatrix}A&O\\O&B\end{bmatrix})=r(\begin{bmatrix}O&A\\B&O\end{bmatrix})=r(A)+r(B)$
    - $r(A)+r(B)\le r(\begin{bmatrix}A&O\\C&B\end{bmatrix})\le r(A)+r(B)+r(C)$
    - $r(AB)\ge r(A)+r(B)-n$
    - $r(A^*)=\begin{cases}n,&r(A)=n,\\1,&r(A)=n-1,\\0,&r(A)<n-1.\end{cases}$
    - $A^2-(k_1+k_2)A+k_1k_2E=O,k_1\ne k_2\Rightarrow r(A-k_1E)+r(A-k_2E)=n$
    - Ax=0的基础解系所含向量的个数$s=n-r(A)$
    - 方程组$A_{m\times n}x=0$与$B_{s\times n}=0$同解$\Leftrightarrow r(A)=r\begin{pmatrix}A\\B\end{pmatrix}=r(B)$
    - $r(I)=r(II)=r(I,II)\Leftrightarrow I\cong II$
    - 若$A\sim \Lambda,$ 则$n_i=n-r(\lambda_iE-A),$其中$\lambda_i$是$n_i$重特征根
    - 若$A\sim\Lambda,$则$r(A)$等于非零特征值的个数，重根按重数计算

{% endmarkmap %}