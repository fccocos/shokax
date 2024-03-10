---
title: 第一章 行列式
categories:
  - 数学
  - 线程代数
tag:
  - 数学
  - - 数学
    - 线性代数
math: true
sticky: true
abbrlink: 1c2ce631
date: 2023-08-17 06:23:22
---



{% markmap 400px %}

- 第一章： 行列式
  - 定义、性质和定理
    - n行列式的定义
    - 行列式的性质
      - 性质1:倒置——$|A|=|A^T|$
      - 性质2:归零——某一行（列）为零，行列式为零。
      - 性质3:比例——任意两行对应成比例或相等，行列式为零
      - 性质4:可拆——任意一行（列）均是两个元素之和，则可将其拆解成两个行列式之和
      - 性质5:互换——任意两行（列）互换，行列式的值为零。
      - 性质6:倍乘——任意一行（列）乘以一个公因子k等于k乘以这个行列式
      - 性质7:倍加——任意一行乘以k加到另一行，则行列式的值不变。
    - 行列式的展开定理
      - 余子式：$M_{ij}$
      - 代数余子式: $A_{ij}=(-1)^{i+j}M_{ij}$
      - 按某行（列）展开的公式: $|A|=\sum_{i=1}^n a_{ij}A_{ij}(j=1,2,\cdots,n)=\sum_{j=1}^n a_{ij}A_{ij}(i=1,2,\cdots,n)$
  - 具体型行列式的计算：$a_{ij}$已经给出
    - 化为基本行列式
      - 上（下）三角：$\begin{vmatrix} a_{11}&a_{12}&\cdots&a_{1n}\\0&a_{22}&\cdots&a_{2n}\\\vdots&\vdots&\ddots&\vdots\\0&0&\cdots&a_{nn}\end{vmatrix}=\begin{vmatrix}a_{11}&0&\cdots&0\\a_{12}&a_{22}&\cdots&0\\\vdots&\vdots&\ddots&\vdots\\a_{1n}&a_{2n}&\cdots&a_{nn}\end{vmatrix}=a_{11}a_{22}\cdots a_{nn}$
      - 主对角: $\begin{vmatrix}a_{11}&\cdots&0\\\vdots&\ddots&\vdots\\0&\cdots&a_{nn}\end{vmatrix}=a_{11}a_{22}\cdots a_{nn}$
      - 副对角: $\begin{vmatrix}0&\cdots&a_{1n}\\\vdots&\dots&\vdots\\a_{1n}&\cdots&0\end{vmatrix}=(-1)^{\frac{n(n-1)}{2}}a_{1n}a_{2n-1}\cdots a_{n1}$
      - 拉普拉斯: $\begin{vmatrix}A&O\\O&B\end{vmatrix}=\begin{vmatrix}A&C\\O&B\end{vmatrix}=\begin{vmatrix}A&O\\C&B\end{vmatrix}=|A||B|$ , $\begin{vmatrix}O&A\\B&O\end{vmatrix}=\begin{vmatrix}C&A\\B&O\end{vmatrix}=\begin{vmatrix}O&A\\B&C\end{vmatrix}=(-1)^{nm}|A||B|$
      - 范德蒙德: $\begin{vmatrix}1&1&\cdots&1\\x_1&x_2&\cdots&x_n\\x_1^2&x_2^2&\cdots&x_n^2\\\vdots&\vdots&\ddots&\vdots\\x_1^n&x_2^n&\cdots&x_n^n\end{vmatrix}=\Pi_{1\le i<j\le n}(x_j-x_i),n\ge 2$
      - 爪形: 斜抓消平（竖）抓
      - 异爪形：阶数不高，直接计算，n很大，则用递推法
    - 加边法（能够该方法的行列式都可以用其他方法写，可以不使用该方法）
    - 递推法（高阶$\to$低阶）
    - 数学归纳法（低阶$\to$高阶）
      - 第一数学归纳法(使用于$F(D_n,D_{n-1})=0$)
        - 验证n=1时，命题成立
        - 假设n=k($k\ge 2$)时，命题成立
        - 证明n=k+1时，命题成立
        - 则命题对于任意正整数n都成立。
      - 第二数学归纳法(使用于$F(D_n, D_{n-1}, D_{n-2})=0$)
        - 验证n=1和n=2时，命题成立
        - 假设n<k时，命题成立
        - 证明n=k($k\ge 3$)时，命题成立
        - 则命题对于任意正整数n都成立。
  - 余子式和代数余子式的计算
    - 行列式法：$k_1A_{i1}+k_2A_{i2}+\cdots+k_nA_{in}=\begin{vmatrix}\vdots&\vdots&\vdots&\vdots\\k_1&k_2&\cdots&k_n\\\vdots&\vdots&\vdots&\vdots\end{vmatrix}$
    - 矩阵法: $A^* = |A|A^{-1}(|A|\ne 0)$
    - 特征值法（三阶且可逆）: $A_{11}+A_{22}+A_{33}=\lambda_2\lambda_3+\lambda_1\lambda_3+\lambda_1\lambda_2$

{% endmarkmap %}

