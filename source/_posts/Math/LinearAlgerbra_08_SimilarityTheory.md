---
title: 第八章 相似理论
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
date: 2023-08-27 10:43:22
---

{% markmap 750px %}

- 相似理论
  
  - A的相似对角化
  
    - 充要条件
      - A有n个线性无关的特性向量$\Leftrightarrow A\sim \Lambda$
      - $n_i=n-r(\lambda_iE-A)\Leftrightarrow A\sim \Lambda$
  
    - 充分条件
      - A是实对称矩阵$\Rightarrow A\sim\Lambda$
      - A有n个互异的特征值$\Rightarrow A\sim\Lambda$
      - $A^2-(k_1+k_2)A+k_1k_2E=O,k_1\ne 0,k_2\ne 0\Rightarrow A\sim\Lambda$
      - $r(A)=1,tr(A)\ne0\Rightarrow A\sim \Lambda$
  
    - 必要条件:$A\sim\Lambda\Rightarrow r(A)=$非零特征值的个数（重根按重数计算）
    - 否定条件
      - $A\ne O,A^k=O$(k为大于1的整数)$\Rightarrow$A不可相似对角化
      - A的特征值全为k但$A\ne kE\Rightarrow A$不可相似对角化
  
  - A相似与B
  
    - 五个性质
      - $|A|=|B|$
      - $r(A)=r(B)$
      - $tr(A)=tr(B)$
      - $\lambda_A=\lambda_B,|\lambda E-A|=|\lambda E-B|$
      - 属于$\lambda_A$的线性无关的特征向量的个数等于属于$\lambda_B$的线性无关的特征向量的个数
  
    - 重要结论
      - $A\sim B\Rightarrow A^T\sim B^T,A^*\sim B^*,A^{-1}\sim B^{-1}$
      - $A\sim B\Rightarrow A^m\sim B^m,f(A)\sim f(B)$
      - $A\sim B,B\sim\Lambda\Rightarrow A\sim\Lambda$
      - $A\sim\Lambda,B\sim\Lambda\Rightarrow A\sim B$
      - $A\sim C,B\sim D\Rightarrow \begin{bmatrix}A&O\\O&B\end{bmatrix}\sim\begin{bmatrix}C&O\\O&D\end{bmatrix}$
  
  - 实对称矩阵与正交矩阵
  
    - 实对称举证的重要结论
  
      - 特征值均为实数，特征向量均为实向量
      - 不同特征值对应的特征向量正交
      - 可用正交矩阵相似对角化
      - A为n阶实对称阵$\Leftrightarrow$A有n个正交的特征向量
  
    - 正交矩阵的重要结论
  
      - $A^TA=E$
        - $\Leftrightarrow$$A^{-1}=A^T$
        - $\Leftrightarrow$$A^T$由规范正交基组成
        - $\Leftrightarrow$$A^T$是正交阵
        - $\Leftrightarrow$$A^*$是正交阵
        - $\Leftrightarrow$$A^{-1}$是正交阵
        - $\Leftrightarrow$$-A$是正交阵
  
  
      -  若A，B为同阶正交矩阵，则AB为正交矩阵，A+B不一定是正交矩阵
      - 若A为正交矩阵，则其实特征值的取值范围为{-1,1}
  

{% endmarkmap %}