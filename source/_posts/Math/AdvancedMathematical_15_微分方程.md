---
title: 第十五章 微分方程
tag:
  - 数学
  - - 数学
    - 高等数学
math: true
sticky: true
abbrlink: bb1bc282
date: 2023-09-02 08:26:12

---

{% markmap 750px %}

- 微分方程

  - 一阶微分方程
    - 能写成$y^{'}=f(x).g(y)$
    - 能写成$y^{'}=f(ax+by+c)$
    - 能写成$y^{'}=f(\frac{y}{x})$
    - 能写成$\frac{1}{y^{'}}=f(\frac{x}{y})$
    - 能写成$y^{'}+p(x)y=q(x)$
    - 能写成$y^{'}+p(x)y=q(x)y^n(n\ne 0,1)$（伯努利方程）
  - 二阶可降阶微分方程的求解
    - 能写成$y{''}=f(x,y^{'})$
    - 能写成$y^{''}=f(y,y^{'})$
  - 高阶系数线性微分方程的求解
    - 能写成$y^{''}+py^{'}+qy=f(x)$
    - 能写成$y^{''}+py^{'}+qy=f_1(x)+f_2(x)$
    - 能写成$x^2y^{''}+pxy^{'}+qy=f(x)$（欧拉方程）
  - 用换元法求解微分方程
    - 用求导公式逆用来换元
    - 用自变量、因变量或x，y地位互换来换元
  - 应用题
    - 用极限、导数或积分等式建方程
    - 用几何应用建方程
      - 用曲线切线斜率
      - 用两曲线$f(x)$与$g(x)$的公切线斜率
      - 用截距
      - 用面积
      - 用体积
      - 用平均值
      - 用弧长
      - 用侧面积
      - 用曲率
      - 用形心
    - 用变化率建方程
  - 差分方程


{% endmarkmap %}

### 微分算子

#### 算子记号

约定：$D=\frac{d}{dx}$, 则有$Dy=\frac{dy}{dx},D^2=\frac{d^2}{dx^2},D^2y=\frac{d^2y}{dx^2}$, 所以从上可以看出D的具体含义是**求导**，而$\frac{1}{D}$是求积分，如$D\sin x= \cos x, D\cos x = -sinx, \frac{\cos x}{D}=\sin x, \frac{\sin x}{D}=-\cos x$

对于微分方程$y^{''}+py^{'}+qy=f(x)$可以用算法表示为$(D^2+pD+q)y=f(x)$,则可令$F(D)=D^2+pD+q$, 则有$F(D)y=f(x)$,所以可以等一个该微分方程的一个特解$y^*=\frac{1}{F(D)}f(x)$

#### 用微分算子求二阶常系数微分方程

##### a. $\frac{1}{F(D)}e^{\alpha x}$型

$$
\begin{flalign}
&\ F(D)|_{x=\alpha}\ne 0 \Rightarrow y^* =\frac{1}{F(D)}e^{\alpha x}=\frac{1}{F(D)|_{x=\alpha}}e^{\alpha x}; &  \\

&\ F(D)|_{x=\alpha}=0, F^{'}(D)|_{x=\alpha}\ne0\Rightarrow y*=\frac{1}{F(D)}e^{\alpha x}=x\frac{1}{F^{'}(D)|_{x=\alpha}}e^{\alpha x}; & \\

&\ F(D)|_{x=\alpha}=0, F^{'}(D)|_{x=\alpha}=0,F^{''}(D)|_{x=\alpha}\ne0\Rightarrow y^* = \frac{1}{F(D)}e^{\alpha x} = x^2\frac{1}{F^{''}(D)_{x=\alpha}}e^{\alpha x}. &
\end{flalign}
$$



##### b. $\frac{1}{F(D^2)}\cos\beta x$或$\frac{1}{F(D^2)}\sin \beta x$(注意：特别约定$F(D^2)=D^2+q$)

$$
\begin{flalign} \label{xc}

&\ F(D^2)|_{D=\beta i}\ne0 \Rightarrow y*=\frac{1}{F(D^2)|_{D=\beta i}} \cos\beta x,y*=\frac{1}{F(D^2)|_{D=\beta i}} \sin\beta x & \\

&\ F(D^2)|_{D=\beta i} = 0, \Rightarrow y^*=x\frac{1}{F(D^2)|_{D=\beta i}}\cos\beta x, y^*=x\frac{1}{F(D^2)|_{D=\beta i}}\sin\beta x &
\end{flalign}
$$

经典例题
$$
y^{''}-3y^{'}+2y=-\frac{1}{2}\cos2x, y^*=?\\
F(D) = D^2-3D+2 \\
y* = \frac{1}{F(D)}\cos\beta x = \frac{1}{D^2-3D+2}(-\frac{1}{2}\cos2x)\\
=\frac{1}{(2i)^2-3D+2}(-\frac{1}{2}\cos2x) \\
=\frac{1}{-4-3D+2}(-\frac{1}{2}\cos2x)\\
=\frac{1}{-2-3D}(-\frac{1}{2}\cos2x)\\
=\frac{1}{3D+2}(\frac{1}{2}\cos2x)\\
=\frac{3D-2}{(3D+2)(3D-2)}(\frac{1}{2}\cos2x)\\
=\frac{3D-2}{9D^2-4}(\frac{1}{2}\cos2x)\\
=\frac{3D-2}{-36-4}(\frac{1}{2}\cos2x)\\
=-\frac{1}{80}(3D-2)\cos2x\\
=-\frac{1}{80}(3D\cos2x-2\cos2x)\\
=-\frac{1}{80}(3D\cos2x-2\cos2x)\\
=\frac{1}{40}(3\sin2x+\cos2x)
$$

##### c. $\frac{1}{F(D)}(x^k+a_1x^{k-1}+a_2x^{k-2}+\cdots+a_{k-1}x+a_k)$型

$y^*=\frac{1}{F(D)}(x^k+a_1x^{k-1}+a_2x^{k-2}+\cdots+a_{k-1}x+a_k)=Q_k(D)(x^k+a_1x^{k-1}+a_2x^{k-2}+\cdots+a_{k-1}x+a_k)$,其中$Q_k(D)$是将$\frac{1}{F(D)}$展开为形式上的泰勒级数.

##### d. $\frac{1}{F(D)}e^{\alpha x}v(x)$型

$y^*=\frac{1}{F(D)}e^{\alpha x}v(x)=e^{\alpha x}\cdot \frac{1}{F(D+\alpha)}v(x)$, $v(x)$为实函数。

### 二阶常系数线性非齐次线性方程

$y^{''}+py^{'}+q=f(x)$对应的特征方程为$r^2+pr+q=0$,

当自由项为$P_n(x)e^{\alpha x}$

如果$p^2-4q>0$, 则特征方程有两个不同的根$r_1,r_2$, 其对应的其次线性微分方程的解为$y_0=C_1e^{r_1x}+C_2e^{r_2x}$, 如果$r_1,r_2$中有一个和$\alpha$相等，则其特解为$y^* = x\cdot Q_n(x)e^{\alpha x}$, 其中$Q_n(x)$为$P_n(x)$所对应的一般多项式,如果$r_1,r_2$中没有一个和$\alpha$相等，则其特解为$y^*=Q_n(x)e^{\alpha x}$

如果$p^2-4q=0$, 则特征方程有一个二重根r, 其对应的其次线性微分方程的解为$y_0=(C_1+C_2x)e^{rx}$, 如果$r$和$\alpha$相等，则其特解为$y^* = x^2\cdot Q_n(x)e^{\alpha x}$, 其中$Q_n(x)$为$P_n(x)$所对应的一般多项式,如果$r$不和$\alpha$相等，则其特解为$y^*=Q_n(x)e^{\alpha x}$

当自由项为$e^{\alpha x}[P_m(x)\cos\beta x+P_n(x)\sin\beta x]$

如果$p^2-4q<0$,则特征方程有为共轭复根$\alpha\pm\beta i$, 其对应的其次线性微分方程的解为$y_0=e^{\alpha x}(C_1\cos\beta x+C_2\sin\beta x)$, 如果$\alpha\pm\beta i$是特征根，则其特解为$y^* = x\cdot e^{\alpha x}(Q_l^{(1)}(x)\cos\beta x+Q_l^{(2)}(x)\sin \beta x)$, 否则为$y^* = e^{\alpha x}(Q_l^{(1)}(x)\cos\beta x+Q_l^{(2)}(x)\sin \beta x)$,其中$l=\max\{m,n\}, Q_l^{(1)}(x),Q_l^{(2)}(x)$分别为x的两个不同的$l$次多项式。



