---
title: 第三章 矩阵运算
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
date: 2023-08-27 05:34:22
---

 {% markmap 750px %}

- 矩阵运算
  - 求$A^n$
    - A为方阵且$r(A)=1\Rightarrow A^n=[tr(A)]^{n-1}A$
    - 试算$A^2$或$A^3$,找规律
      - $A^2=kA\Rightarrow A^n = k^{n-1}A$
      - $A^2=kE\Rightarrow \begin{cases}A^{2n}=k^nE\\A^{2n+1}=k^nA\end{cases}$
    - A分解为B+C
      - $A=B+C,BC=CB\Rightarrow A^n = B^n+C_n^1B^{n-1}C+C_n^2B^{n-2}C^2+\cdots+C_n^{n-1}BC^{n-1}+C^n$
      - $A=B+C,BC=CB,B=E\Rightarrow A^n = E+C_n^1C+C_n^2C^2+\cdots+C_n^{n-1}C^{n-1}+C^n$
      - $A=B+C,BC=CB=O\Rightarrow A^n=B^n+C^n$
    - 用初等矩阵知识求$P_1^mAP_2^n$
      - $P_1,P_2$ 为初等矩阵，m,n为正整数，则$P_1^mAP_2^n$表示先对A做了与$P_1$相同的初等行变换，且重复了m次；在对$P_1^mA$做了与$P_2$相同的初等列变换，且重复了n次
    - 用相似理论求$A^n$
      - $A\sim B\Rightarrow A=PBP^{-1},A^n=PB^nP^{-1}$
      - $A\sim \Lambda\Rightarrow A=P\Lambda P^{-1},A^n=P\Lambda^nP^{-1}$
  - 关于$A^*,A^{-1}$与初等矩阵
    - $A^*$
      - 定义：$A^*=\begin{bmatrix}A_{11}&A_{12}&\cdots&A_{1n}\\A_{21}&A_{22}&\cdots&A_{2n}\\\vdots&\vdots&\ddots&\vdots\\A_{n1}&A_{n2}&\cdots&A_{nn}\end{bmatrix}$
      - 公式：
        - $AA^*=A^*A=|A|E$
        - $|A^*|=|A|^{n-1}$
        - $(A^T)^*=(A^*)^T$
        - $(kA)^*=k^{n-1}A*,(-A)^*=(-1)^{n-1}A^*$
        - $A^{-1}=\frac{1}{|A|}A^*$
        - $A^*=|A|A^{-1}$
        - $(A^*)^{-1}=\frac{1}{|A|}A=(A^{-1})^*$
        - $(A^*)^*=|A|^{n-2}A$
        - $|(A^*)^*|=|A|^{(n-1)^2}$
        - $(AB)^*=B^*A^*$
      - 秩
    - $A^-1$
      - 定义：对于方阵$A,B$,若$AB=E$,则$A,B$互为逆矩阵，且$A^{-1}=B,B^{-1}=A,AB=BA$
      - 性质
        - $(A^{-1})^{-1}=A$
        - $(AB)^{-1}=B^{-1}A^{-1}$
        - $k\ne 0,(kA)^{-1}=\frac{1}{k}A^{-1}$
        - $(A^T)^{-1}=(A^{-1})^T$
        - $|A^{-1}|=\frac{1}{|A|}$
      - 求$A^{-1}$
        - 具体型
          - $A^{-1}=\frac{1}{|A|}A$
          - 初等行变换：$[A\vdots E]\Leftrightarrow [E\vdots A^{-1}]$
        - 抽象型
          - $AB=E\Leftrightarrow A^{-1}=B$
          - $A=BC$且B,C为可逆举证$\Rightarrow A^{-1}=C^{-1}B^{-1}$
      - 初等矩阵
        - 定义
          - 初等变换：
            - 一个非零常数乘矩阵的某一行（列）
            - 互换矩阵中某两行（列）位置
            - 矩阵的某一行（列）的k倍加到另一行（列）
          - 初等矩阵
            - 有单位矩阵记过一次初等行变换得到的矩阵
          - 矩阵等价
            - $A,B$均是$m\times n$的矩阵，若存在可逆矩阵$P_{m\times m},Q_{n\times n},$使得$PAQ=B$, 则$A\cong B$
        - 性质
          - $|E_{ij}|=-1,|E_{ij}(k)|=1,|E_i(k)|=k$
          - $E_{ij}^T=E_{ij}, E_{ij}^T(k)=E_{ji}(k),E_i^T(k)=E_i^T(k)$
          - $E_{ij}^{-1}=E_{ij},E_{ij}^{-1}(k)=E_{ij}(-k),E_i^{-1}(k)=E_i(\frac{1}{k})$
          - $E_{ij}^*=|E_{ij}|E_{ij}^{-1}=-E_ij,\\E_{ij}^*(k)=|E_{ij}(k)|E_{ij}^{-1}(k)=E_{ij}(-k)\\E_i^*(k)=|E_i(k)|E_i^{-1}(k)=kE_i(\frac{1}{k})$
        - 左行右列定理
        - 应用
          - 求$A^{-1}$：初等行变换、初等列变换
          - 研究$P_1^mAP_2^n=B$
      - 分块矩阵
        - 定义：用几条横线和纵线把一个矩阵分成若干小块，每一小块称为原矩阵的子块，把子块看作原矩阵的一个元素，就得到了分块矩阵
        - 运算
          - 转置
          - 加法
          - 数乘
          - 乘法
          - 若A，B分别为m，n阶方阵，则分块对角矩阵的幂为$\begin{bmatrix}A&O\\O&B\end{bmatrix}^k=\begin{bmatrix}A^k&O\\O&B^k\end{bmatrix}$
          - 设B为r阶可逆矩阵，C是s阶可逆矩阵，则以下矩阵可逆，且
            - $\begin{bmatrix}B&O\\D&C\end{bmatrix}^{-1}=\begin{bmatrix}B^{-1}&O\\-C^{-1}DB^{-1}&C^{-1}\end{bmatrix}$
            - $\begin{bmatrix}B&D\\O&C\end{bmatrix}^{-1}=\begin{bmatrix}B^{-1}&-B^{-1}DC^{-1}\\O&C^{-1}\end{bmatrix}$
            - $\begin{bmatrix}O&B\\C&D\end{bmatrix}^{-1}=\begin{bmatrix}-C^{-1}DB^{-1}&C^{-1}\\B^{-1}&O\end{bmatrix}$
            - $\begin{bmatrix}D&B\\C&O\end{bmatrix}^{-1}=\begin{bmatrix}O&C^{-1}\\B^{-1}&-B^{-1}DC^{-1}\end{bmatrix}$
          - 主对角线分块矩阵$A=\begin{bmatrix}A_1&&&\\&A_2&&\\&&\ddots&\\&&&A_s\end{bmatrix},$若$A_i(i=1,2,\cdots,s)$均可逆，则A可逆，且$A^{-1}=\begin{bmatrix}A_1^{-1}&&&\\&A_2^{-1}&&\\&&\ddots&\\&&&A_s^{-1}\end{bmatrix},$
          - 副对角线分块矩阵$A=\begin{bmatrix}&&&A_1\\&&A_2&\\&\ldots&&\\A_s&&&\end{bmatrix},$若$A_i(i=1,2,\cdots,s)$均可逆，则A可逆，且$A^{-1}=\begin{bmatrix}&&&A_S^{-1}\\&&\ldots&\\&A_2^{-1}&&\\A_1^{-1}&&&\end{bmatrix}$
          -  舒尔公式：
            - $\begin{bmatrix}E_r&O\\-CA^{-1}&E_{n-r}\end{bmatrix}\begin{bmatrix}A&B\\C&D\end{bmatrix}=\begin{bmatrix}A&B\\O&D-CA^{-1}B\end{bmatrix}$
            - $\begin{bmatrix}A&B\\C&D\end{bmatrix}\begin{bmatrix}E_r&-A^{-1}B\\O&E_{n-r}\end{bmatrix}=\begin{bmatrix}A&O\\C&D-CA^{-1}B\end{bmatrix}$
            - $\begin{bmatrix}E_r&O\\-CA^{-1}&E_{n-r}\end{bmatrix}\begin{bmatrix}A&B\\C&D\end{bmatrix}\begin{bmatrix}E_r&-A^{-1}B\\O&E_{n-r}\end{bmatrix}=\begin{bmatrix}A&O\\O&D-CA^{-1}B\end{bmatrix}$
        - 矩阵方程
          - 定义：含有未知矩阵的方程
          - 化简
            - 消公因式：$CA=CB$且C可逆，则$A=B$
            - 提取公因式：$CA+CB=C(A+B)$
            - 移项：将已知表达式和未知表达式分贝移至方程的两边
            - 利用公式
          - 求解
            - 若A可逆或B可逆，或A，B可逆，则分别可得解$X=A^{-1}B,X=BA^{-1},X=A^{-1}CB^{-1}$
            - 若A不可逆，如$AX=B$，则将X和B按列分块，得$A[\xi_1,\xi_2,\cdots,\xi_n]=[\beta_1,\beta_2,\cdots,\beta_n],$即$A\xi_i=\beta_i,i=1,3,\cdots,n.$求上述线程方程，得解 $\xi_i$,从而得$X=[\xi_1,\xi_2,\cdots,\xi_n]$
            - 

{% endmarkmap %}