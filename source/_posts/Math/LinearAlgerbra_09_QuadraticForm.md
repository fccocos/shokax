---
title: 第九章 二次型
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
date: 2023-08-27 12:43:22
---

{% markmap 750px %}

- 二次型
  - 二次型及其标准、规范形
    - 二次型的矩阵表示及其秩：$f(x)=xA^Tx,$ 其中$A=A^T,A$的秩称为二次型f的秩
    - 线性变换：$x=Cy$
    - 二次型的标准形、规范形
      - 定义
        - 标准形：$d_1x_1^2+d_2x_2^2+\cdots+d_nx_n^2$
        - 规范形：$x_1^2+\cdots+x_p^2-x_{p+1}^2-\cdots-x_{p+q}^2$
  
      - 重要结论
        - 任何二次型$f=x^TAx$均可通过配方法（作可逆线性变换$x=Cy$）化成标准形$k_1y_1^2+k_2y_2^2+\cdots+k_ny_n^2$或规范形$y_1^2+\cdots+y_p^2-y_{p+1}^2\cdots-y_{p+q}^2$
        - 任何二次型$f=x^TAx$也可以通过正交变换$x=Qy$化为标准形$\lambda_1y_1^2+\lambda_2y_2^2+\cdots+\lambda_ny_n^2$
        - (惯性定理)无论选取什么样的可逆线性变换，将二次型化为标准形或规范形，其正项个数p，负项个数q都是不变的，p称为正惯性指数，q称为负惯性指数。
  
  - 配方法
    - 含平方项：将某个变量的平方项及与其有关的混合项合并在一起，配成一个完全平方项，如法炮制，直至配完。
    - 不含平方项：创造平方项吗，如含有$x_1x_2$项，令$\begin{cases}x_1=y_1+y_2,\\x_2=y_1+y_2,\end{cases}$使$x_1x_2=y_1^2-y_2^2,$出现平方项，再按含平方项的方法配方
    - 矩阵语言：对实对称矩阵A，必存在可逆矩阵C，使得$C^TAC=\Lambda,$其中$\Lambda$是对角矩阵
  
  - 正交变换法
    - 基本步骤
      - 在确定A是实对称矩阵的条件下，求A的特征值$\lambda_1,\lambda_2,\cdots,\lambda_n$
      - 求A对应与特征值$\lambda_1,\lambda_2,\cdots,\lambda_n$的特征向量$\xi_1,\xi_2,\cdots,\xi_n$
      - 将$\xi_1,\xi_2,\cdots,\xi_n$正交化、单位化为$\eta_1,\eta_2,\cdots,\eta_n$
      - 令$Q=[\eta_1,\eta_2,\cdots,\eta_n],$则Q为正交阵，且$Q^{-1}AQ=Q^TAQ=\Lambda$.
      - 于是$f=x^TAx=(Qy)^TA(Qy)=y^TQ^TAQy=y^T\Lambda y$
  
    - 反求参数，A或f
    - 最值问题
      - A的特征值大小排序$\lambda_1\le\lambda_2\le\cdots\le\lambda_n$
        - $\lambda_1x^Tx\le x^TAx\le \lambda_nx^Tx$
        - $x^Tx=1\Rightarrow f_{min}=\lambda_1,f_{max}=\lambda_n$
  
    - 几何应用
      - $\lambda_1,\lambda_2,\lambda_3$的符号为3正，$f(x_1,x_2,x_3)=1$为椭球面
      - $\lambda_1,\lambda_2,\lambda_3$的符号为2正1负，$f(x_1,x_2,x_3)=1$为单叶双叶曲面
      - $\lambda_1,\lambda_2,\lambda_3$的符号为1正2负，$f(x_1,x_2,x_3)=1$为双叶双曲面
      - $\lambda_1,\lambda_2,\lambda_3$的符号为2正1零，$f(x_1,x_2,x_3)=1$为椭圆柱面
      - $\lambda_1,\lambda_2,\lambda_3$的符号为1正1负1零，$f(x_1,x_2,x_3)=1$为双曲柱面
  
  - 实对称矩阵的合同
    - 同阶实对称矩阵A，B合同的判定
      - 定义法
      - 正、负惯性指数
      - 传递性
      - 相似
  
    - 已知$A,\Lambda(\Lambda$为对角阵),求可逆阵C，使得$C^TAC=\Lambda$
    - 已知A,B(B为对角阵)，求可逆矩阵C，使得$C^TAC=B$
  
  - 正定二次型
    - 前提：$A=A^T$
    - 二次型$f=x^TAx$正定的充要条件
      - 对于任意$x\ne 0$，有$x^TAx>0$（定义）
      - A的特征值$\lambda_i>0(i=1,2,\cdots,n)$
      - f的正惯性指数p=n
      - 存在可逆阵D，使得$A=D^TD$
      - A与E合同
      - A的各阶顺序主子式均大于0
  
    - 二次型$f=x^TAx$正定的必要条件
      - $a_{ii}>0$
      - $|A|>0$
  
    - 重要结论
      - 若A正定，则$A^{-1},A^*,A^m(m\in N^+),kA(k>0),C^TAC$均正定
      - 若A,B正定，则A+B正定，$\begin{bmatrix}A&O\\O&B\end{bmatrix}$正定
      - 若A，B正定，则AB正定的充要条件是AB=BA
      - 若A正定且是正交矩阵，则A=E
  

{% endmarkmap %}