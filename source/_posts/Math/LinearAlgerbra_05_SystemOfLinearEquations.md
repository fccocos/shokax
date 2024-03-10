---
title: 第五章 线性方程组
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

- 线性方程组
  - 具体型方程组
    - 齐次线性方程组
      - 解的性质：$\xi_1,\xi_2$是$Ax=0$的解，则$k_1\xi_1+k_2\xi_2$也是它的解$(k_1,k_2\in R)$
      - 基础解系：
        - 是解
        - 线程无关
        - $s=n-r(A)$
      - 齐次线性方程组有非零解的充要条件及其通解
        - 充要条件：$r(A)<n$
        - 通解：$x=k_1\xi_1+k_2\xi_2+\cdots+k_{n-r}\xi_{n-r}$
    - 非齐次线程方程组
      - 解的性质：$\eta_1,\eta_2$是Ax=b的通解，则$\eta_1-\eta_2$是$Ax=0$的解
      - 非齐次线性方程组的情形
        - $r(A)=r([A\vdots b])=n$时，方程组有唯一解
        - $r(A)=r([A\vdots b])<n$时，方程组有无穷多解
        - $r(A)\ne r([A\vdots b])$时，方程组无解
      - 非齐次线性方程组的通解：$x=\eta^*+k_1\xi_1+k_2\xi_2+\cdots+k_{n-r}\xi_{n-r}$
    - 解线性方程组
      - 用初等行变换将齐次方程组的系数矩阵或非齐次线性方程组的增广矩阵化为阶梯型矩阵，再用方程组理论判别、求解
      - “方形”(方程个数等于未知数个数)的方程组
        - $|A|\ne 0\Leftrightarrow$方程组有唯一解$\Leftrightarrow f(\lambda)\ne 0$
        - $|A|=0\Leftrightarrow f(\lambda)=0$
        - 变体形式：含参数的向量之间的线性关系
    - 公共解与同解问题
      - 公共解
        - 联立方程$\begin{bmatrix}A\\B\end{bmatrix}x=0$的解
        - 求出$A_{m\times n}x=0$的通解$k_1\xi_1+k_2\xi_2+\cdots+k_s\xi_s,$代入$B_{m\times n}x=0,$求出$k_i$之间的关系，回代$A_{m\times n}x=0$的通解
        - 给出$A_{m\times n}=0$ 的基础解系$\xi_1,\xi_2,\cdots,\xi_s$与$\eta_1,\eta_2,\cdots,\eta_t$,则公共解$\gamma = k_1\xi_1+k_2\xi_2+\cdots+k_s\xi_s=l_1\eta_1+l_2\eta_2+\cdots+l_t\eta_t$
      - 同解方程组
        - $Ax=0,Bx=0$时通解方程组$\Leftrightarrow$$Ax=0$的解满足$Bx=0$，且$Bx=0$的解满足$Ax=0$$\Leftrightarrow$$r(A)=r(B),$且$Ax=0$的解满足$Bx=0$$\Leftrightarrow$$r(A)=r(B)=r(\begin{bmatrix}A\\B\end{bmatrix})$
  - 抽象型方程组
    - 解的判定
      - $A_{m\times n}x=0$
        - $r(A)=n,$只有零解
        - $r(A)<n,$有无穷多解
      - $A_{m\times n}x=b$
        - $r(A)\ne r([A\vdots b]),$无解
        - $r(A)=r([A\vdots b])=n,$有唯一解
        - $r(A)=r([A\vdots b])<n,$有无穷多解
    - 基础解系与解的结构
      - 解除解系
      - 解的结构
    - 解与系数的关系
  - 线程方程组的几何意义

{% endmarkmap %}