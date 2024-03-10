---
title: 第二章 矩阵
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
date: 2023-08-20 08:52:22
---

{% markmap 750px %}

- 矩阵

  - 矩阵的定义及基本运算

    - 定义：由$m\times n$个数$a_{ij}(i=1,2,\cdots,m;j=1,2,\cdots,n)$组成的m行n列的矩形表格

    - 基本运算

      - 相等：$A=(a_{ij})_{m\times n}, B=(b_{ij})_{m\times n}, a_{ij}=b_{ij}\Rightarrow A=B$
      - 加法:$A=\begin{bmatrix}a_{11}&a_{12}&\cdots&a_{1n}\\a_{21}&a_{22}&\cdots&a_{2n}\\\vdots&\vdots&\ddots&\vdots\\a_{n1}&a_{n2}&\cdots&a_{nn} \end{bmatrix}, B=\begin{bmatrix}b_{11}&b_{12}&\cdots&b_{1n}\\b_{21}&b_{22}&\cdots&b_{2n}\\\vdots&\vdots&\ddots&\vdots\\b_{n1}&b_{n2}&\cdots&b_{nn} \end{bmatrix}\Rightarrow A+B=\begin{bmatrix}a_{11}+b_{11}&a_{12}+b_{12}&\cdots&a_{1n}+b_{1n}\\a_{21}+b_{21}&a_{22}+b_{22}&\cdots&a_{2n}+b_{2n}\\\vdots&\vdots&\ddots&\vdots\\a_{n1}+b_{n1}&a_{n2}+b_{n2}&\cdots&a_{nn}+b_{nn} \end{bmatrix}$
      - 数乘矩阵: $A=\begin{bmatrix}a_{11}&a_{12}&\cdots&a_{1n}\\a_{21}&a_{22}&\cdots&a_{2n}\\\vdots&\vdots&\ddots&\vdots\\a_{n1}&a_{n2}&\cdots&a_{nn} \end{bmatrix}\Rightarrow kA=\begin{bmatrix}ka_{11}&ka_{12}&\cdots&ka_{1n}\\ka_{21}&ka_{22}&\cdots&ka_{2n}\\\vdots&\vdots&\ddots&\vdots\\ka_{n1}&ka_{n2}&\cdots&ka_{nn} \end{bmatrix}$
      - 矩阵的乘法: $A_{ms}\times B_{sn}= C_{mn}, c_{ij}=\sum\limits_{k=1}^s a_{ik}b_{kj}$
        - 结合律：$(A_{ms}B_{sr})C_{rn} = A_{ms}(B_{sr}C_{rn})$
        - 分配律：$A_{ms}(B_{sn}+C_{sn})=A_{ms}B_{sn}+A_{ms}C_{sn}; (B_{sn}+C_{sn})A_{ms}=B_{sn}A_{ms}+C_{sn}A_{ms}$

      - 转置矩阵: $A=\begin{bmatrix}a_{11}&a_{12}&\cdots&a_{1n}\\a_{21}&a_{22}&\cdots&a_{2n}\\\vdots&\vdots&\ddots&\vdots\\a_{n1}&a_{n2}&\cdots&a_{nn} \end{bmatrix}\Rightarrow A^T = \begin{bmatrix}a_{11}&a_{21}&\cdots&a_{n1}\\a_{12}&a_{22}&\cdots&a_{n2}\\\vdots&\vdots&\ddots&\vdots\\a_{1n}&a_{2n}&\cdots&a_{nn} \end{bmatrix}$
        - $(A^T)^T=A$
        - $(kA)^T = kA^T$
        - $(A+B)^T=A^T+B^T$
        - $(AB)^T=B^TA^T$
        - $|A^T|=|A|$
      - 向量的内积与正交
        - 内积:$\overrightarrow\alpha = [a_1, a_2,\cdots,a_n]^T, \overrightarrow\beta = [b_1,b_2,\cdots,b_n]^T \Rightarrow \overrightarrow\alpha\cdot\overrightarrow\beta = \sum\limits_{i=1}^n a_ib_j$，即$(\overrightarrow\alpha,\overrightarrow\beta) = {\overrightarrow\alpha}^T\overrightarrow\beta$
        - 正交：$(\alpha,\beta)=0$
        - 模: $||\alpha||=\sqrt{\sum\limits_{i=1}^sa_i^2}$
        - 标准正交向量组:$a_i^Ta_j = \begin{cases}0,&i\ne j,\\1,&i=j \end{cases}$
      - 施密特正交化
        - 正交化
          - $\beta_1=\alpha_1$
          - $\beta_2=\alpha_2-\frac{(\alpha_2,\beta_1)}{(\beta_1,\beta_1)}\beta_1$
        - 单位化
          - $\eta_1 = \frac{\beta_1}{||\beta_1||}$
          - $\eta_2=\frac{\beta_2}{||\beta_2||}$
      - 矩阵的幂
        - $(A+B)^2 = A^2 + AB + BA + B^2 \ne A^2 + 2AB + B^2$
        - $(A-B)^2 = A^2 - AB - BA + B^2 \ne A^2 - 2AB + B^2$
        - $(A+B)(A-B)= A^2 - AB + BA  - B^2 \ne A^2 - B^2$
        - $(AB)^m = \overbrace{(AB)(AB)\cdots(AB)}^{m}\ne A^mB^m$
        - $f(x)=a_0+a_1x+a_2x^2+\cdots+a_nx^n\Rightarrow f(A)=a_0E+a_1A+a_2A^2+\cdots+a_nA^n$
      - 方阵乘积的行列式: $|AB|=|A||B|$
        - 零矩阵：$O$
        - 单位阵: $E$
        - 数量阵：$kE$
        - 对角阵: $diag(a_1,a_2,\cdots,a_n)$
        - 上（下）三角阵
        - 对称阵: $A^T = A$
        - 反对称阵：$A^T = -A$
        - 正交阵: $A^TA=E \Rightarrow$A的行列向量组是标准正交向量组
        - 分块阵

  - 矩阵的逆

    - 定义：如果$AB=BA=E$,则称A位可逆矩阵，并称B是A的逆矩阵，且逆矩阵唯一，记作$A^{-1}$
    - 矩阵可逆的充要条件：A可逆$\Leftrightarrow AA^*=|A|E$
    - 性质与公式
      - $(A^{-1})^{-1} = A$
      - $(kA)^{-1}=\frac{1}{k}A^{-1}$
      - $(AB)^{-1}=B^{-1}A^{-1}$
      - $(A^T)^{-1}=(A^{-1})^T$
      - $|A^{-1}|=|A|^{-1}$

    - 用定义求逆矩阵: 
      - $AB=E\Rightarrow A^{-1} = B$
      - A为可逆阵且A=BC$\Rightarrow A^{-1}=C^{-1}B^{-1}$
      - A,B均为可逆阵$\Rightarrow \begin{bmatrix}A&O\\O&B \end{bmatrix}^{-1}=\begin{bmatrix}A^{-1}&O\\O&B^{-1}\end{bmatrix},\begin{bmatrix}O&A\\B&O \end{bmatrix}^{-1}=\begin{bmatrix}O&B^{-1}\\A^{-1}&O\end{bmatrix}$

  - 伴随矩阵

    - 定义：$AA^*=A^*A=|A|E$
    - 性质与公式(A为可逆阵)
      - $|A^*|=|A|^{n-1}$
      - $A^*=|A|A^{-1}$
      - $(kA)(kA)^*=|kA|E$
      - $A^T(A^T)^*=|A^T|E$
      - $A^{-1}(A^{-1})^*=|A^{-1}|E$
      - $A^*(A^*)^*=|A^*|E$
      - $(A^T)^* = (A^*)^T$
      - $(A^{-1})^*=(A^*)^{-1}$
      - $(AB)^* = B^*A^*$
      - $(A^*)^*=|A|^{n-2}A$
    - 用伴随矩阵求逆矩阵: $A^{-1}=\frac{A^*}{|A|}$

  - 初等变换与初等矩阵

    - 初等变换
      - 倍乘
      - 倍加
      - 互换
    - 初等矩阵
      - 定义
        - 倍乘：$E_i(k)$
        - 倍加：$E_{ij}(k)$（将第j行乘k加到第i行，或者将第i列乘k加到第j列）
        - 互换：$E_{ij}$(将第i行和第j行互换，或者将第i列与第j列互换)
      - 性质与公式
        - 转置后的初等矩阵仍然是初等矩阵
        - 初等矩阵均可逆，且其可逆阵属于同一类型的初等矩阵
          - $[E_i(k)]^{-1}=E_i(\frac{1}{k})$
          - $[E_{ij}(k)]^{-1}=E_{ij}(-k)$
          - $E_{ij}^{-1} = E_{ij}$
        - A为可逆阵矩阵，则A可以经过有限次初等变换化为单位阵E
        - 左行右列：初等行变换$\Leftrightarrow$左乘一个初等矩阵；初等列变换$\Leftrightarrow$右乘一个初等矩阵 
      - 用初等变换（初等矩阵）求逆矩阵
        - $[A\vdots E] = [E\vdots A^{-1}]$
    - 矩阵方程
      - $AX=B$
      - $XA=B$
      - $AXB=C$
    - 矩阵的秩与等价矩阵
      - 秩
        - 定义: $r(A)=n\Leftrightarrow |A|\ne 0 \Leftrightarrow A$可逆
        - 初等变换不改变矩阵的秩：$A_{mn},P_{mm},Q_{nn}\Rightarrow r(A)=r(PA)=r(AQ)=r(PAQ)$,其中P、Q为可逆阵。
        - 几个重要式子
          - $0\le r(A) \le \min\{m,n\}$
          - $r(kA)=r(A)$
          - $r(AB)\le \min\{r(A), r(B)\}$
          - $r(A+B)\le r(A)+r(B)$
          - $r(A^*)=\begin{cases}n,&r(A)=n,\\1,&r(A)=n-1,\\0,&r(A)<n-1.\end{cases}$
      - 等价矩阵

{% endmarkmap %}