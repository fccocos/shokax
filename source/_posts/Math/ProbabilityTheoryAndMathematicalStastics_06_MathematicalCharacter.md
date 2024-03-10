---
title: 第六章 数字特征
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
date: 2023-08-28 16:18:08
---

{% markmap 750px %}

- 数字特征
  - 数学期望
    - X
      - $X\sim p_i\Rightarrow EX=\sum\limits_ix_ip_i$
        - 有限项相加
        - 无穷项相加（无穷级数）

      - $X\sim f(x)\Rightarrow EX=\int_{-\infty}^{+\infty}xf(x)dx$
        - 有限区间积分（定积分）
        - 无穷区间积分（反常积分）

    - $g(X)$
      - $X\sim p_i,Y=g(X)\Rightarrow EY=\sum\limits_ig(x_i)p_i$
      - $X\sim f(x),Y=g(x)\Rightarrow EX=\int_{-\infty}^{+\infty}g(x)f(x)dx$

    - $g(X,Y)$
      - $(X,Y)\sim p_{ij},Z=g(X,Y)\Rightarrow EZ=\sum\limits_i\sum\limits_jg(x_i,y_j)p_{ij}$
      - $(X,Y)\sim f(x,y),Z=g(X,Y)\Rightarrow EZ=\int_{-\infty}^{+\infty}\int_{-\infty}^{+\infty}g(x,y)f(x,y)dxdy$

    - 最值
      - $Y=\min\{X_1,X_2,\cdots,X_n\},EY=\int_{-\infty}^{+\infty}yf_Y(y)dy,$其中$f_Y(y)=n[1-F(y)]^{n-1}f(y)$
      - $Z=\min\{X_1,X_2,\cdots,X_n\},EZ=\int_{-\infty}^{+\infty}zf_Z(z)dy,$其中$f_Z(z)=n[F(z)]^{n-1}f(z)$

    - 分解：$D(X_1+X_2+\cdots+X_n)=EX_1+EX_2+\cdots+EX_n$
    - 性质： 
      - $Ea=a,E(EX)=EX$
      - $E(aX+bY)=aEX+bEY,E(\sum\limits_{i=1}a_iX_i)=\sum\limits_{i=1}^na_iEX_i$
      - 若X,Y相互独立，则$E(XY)=EXEY$
  - 方差
    - X
      - 定义：$DX=E[(X-EX)^2]$
      - 定义法：
        - $X\sim p_i\Rightarrow DX=E(X-EX)^2=\sum\limits_i(x_i-EX)^2p_i$
        - $X\sim f(x)\Rightarrow DX=E[(X-EX)^2]=\int_{-\infty}^{+\infty}(x-EX)^2f(x)dx$
  
      - 公式法
        - $DX=E(X^2)-(EX)^2$
  
      - 最值
        - $Y=\min\{X_1,X_2,\cdots,X_n\},E(Y^2)=\int_{-\infty}^{+\infty}y^2f_Y(y)dy\Rightarrow DY=E(Y^2)-(EY)^2$
        - $Z=\max\{X_1,X_2,\cdots,X_n\},E(Z^2)=\int_{-\infty}^{+\infty}z^2f_Z(z)dz\Rightarrow DZ=E(Z^2)-(EZ)^2$
  
      - 分解：$D(X_1+X_2+\cdots+x_n)=DX_1+DX_2+\cdots+DX_n+2\sum\limits_{1\le i<j \le n}Cov(X_i,X_j)=DX_1+DX_2+\cdots+DX_n$
  
    - 性质
      - $DX\ge 0, E(X^2)=DX+(EX)^2\ge (EX)^2$
      - $Dc=0$(c为常数)
      - $DX=0\Leftrightarrow X$几乎处处为某个常数a，即$P\{X=a\}=1$
      - $D(aX+b)=a^2DX$
      - $D(X\pm Y)=DX+DY\pm 2Cov(X,Y)$
      - $D(\sum\limits_{i=1}^na_iX_i)=\sum\limits_{i=1}^na_i^2DX_i+2\sum\limits_{1\le i<j\le n}a_ia_jCov(X_i,X_j)$
      - $D(aX+bY)=a^2DX+b^2DY$
      - $D(XY)=DXDY+DX(EY)^2+DY(EX)^2+DY(EX)^2\ge DXDY$
      - 对任意常数c，有$DX=E[(X-EX)^2]\le E[(X-c)^2]$
  - 常用分布的$EX,DX$
    - 0-1分布，$EX=p,DX=p-p^2=(1-p)p$
    - $X\sim B(n,p), EX=np, DX=np(1-p)$
    - $X\sim P(\lambda), EX=\lambda,DX=\lambda^2$
    - $X\sim G(p),EX=\frac{1}{p},DX=\frac{1-p}{p^2}$
    - $X\sim U(a,b),EX=\frac{a+b}{2},DX=\frac{(b-a)^2}{12}$
    - $X\sim E(\lambda),EX=\frac{1}{\lambda},DX=\frac{1}{\lambda^2}$
    - $X\sim N(\mu,\sigma^2),EX=\mu,DX=\sigma^2$
    - $X\sim \varkappa^2(n),EX=n,DX=2n$
  - 协方差$Cov(X,Y)$与相关系数$\rho_{XY}$
    - $Cov(X,Y)$
      - 定义：$Cov(X,Y)=E[(X-EX)(Y-EY)]$
      - 定义法：
        - $(X,Y)\sim p_{ij}\Rightarrow Cov(X,Y)=\sum\limits_i\sum\limits_j(x_i-EX)(y_j-EY)p_{ij}$
        - $(X,Y)\sim f(x,y)\Rightarrow Cov(X,Y)=\int_{-\infty}^{+\infty}\int_{-\infty}^{+\infty}(x-EX)(y-EY)f(x,y)dxdy$
      - 公式法：$Cov(X,Y)=E(XY)-EXEY$
      - $\rho_{xy}$定义：$\rho_{xy}=\frac{Cov(X,Y)}{\sqrt{DX}\sqrt{DY}}\begin{cases}=0\Leftrightarrow X,Y&Not Relative\\\ne0 \Leftrightarrow X,Y&Relative\end{cases}$
      - 性质
        - $Cov(X,Y)=Cov(X,Y)$
        - $Cov(aX,bY)=abCov(X,Y)$
        - $Cov(X_1+X_2,Y)=Cov(X_1,Y)+Cov(x_2,Y)$
        - $|\rho_{XY}|\le 1$
        - $\rho_{XY}=1\Leftrightarrow P\{Y=aX+b\}=1(a>0)$
        - $\rho_{XY}=-1\Leftrightarrow P\{Y=aX+b\}=1(a<0)$
        - $\rho_{XY}=0\Leftrightarrow Cov(X,Y)=0\Leftrightarrow E(XY)=EXEY\Leftrightarrow D(X+Y)=DX+DY\Leftrightarrow D(X-Y)=DX+DY$
        - X,Y独立$\Rightarrow\rho_{XY}=0$
        - 若$(X,Y)\sim N(\mu_1,\mu_2;\sigma_1^2,\sigma_2^2;\rho_{XY}),$则X与Y相互独立$\Leftrightarrow$X,Y不相关($\rho_{XY}=0$)
  - 独立性与不相关性的判定
    - 用分布判独立
      - 若$(X,Y)$是连续型的，则X与Y相互独立的充要条件是$f(x,y)=f_X(x)\cdot f_Y(y)$
      - 若$(X,Y)$是离散型的，则X与Y相互独立的充要条件是$P\{X=x_i,Y=y_i\}=P\{X=x_i\}\cdot P\{Y=y_j\}$
    - 用数字特征判不相关：$\rho_{XY}=0\Leftrightarrow Cov(X,Y)=0\Leftrightarrow E(XY)=EXEY\Leftrightarrow D(X\pm Y)=DX + DY$
    - 步骤：先计算中$Cov(X,Y)$,而后按下列步骤进行判断或再计算：$Cov(X,Y)=E(XY)-EXEY$
      - $\ne 0\Leftrightarrow$X和Y相关$\Rightarrow$X与Y不独立
      - $=0\Leftrightarrow$X与Y不相关,通过分布推断
        - X，Y独立
        - X，Y不独立
    - 重要结论
      - 如果X与Y独立，则X与Y不相关，反之不然
      - 如果X与Y相关，则X，Y不独立
      - 如果$(X,Y)$服从二维正态分布，则X，Y独立$\Leftrightarrow$X,Y不相关
      - 如果X与Y均服从0-1分布，则X，Y独立$\Rightarrow$X,Y不相关
  - 切比雪夫不等式
    - $P\{|X-EX|\ge \varepsilon\}\le \frac{DX}{\varepsilon^2}$
    - $P\{|X-EX|<\varepsilon\}\ge 1- \frac{DX}{\varepsilon^2}$


{% endmarkmap %}

$X\sim p_i\Rightarrow EX=\sum\limits_ix_ip_i$

$X\sim f(x)\Rightarrow EX=\int_{-\infty}^{+\infty}xf(x)dx$