---
title: 第十六章 无穷级数
tag:
  - 数学
  - - 数学
    - 高等数学
math: true
sticky: true
abbrlink: bb1bc282
date: 2023-09-02 09:08:12

---

{% markmap 750px %}

- 无穷级数

  - 数项级数的判敛
    - 定义与$S_n$
    - 判敛法
      - 正项级数$\sum\limits_{n=1}^{\infty}u_n,u_n\ge0$
      - 交错级数$\sum\limits_{n=1}^{\infty}(-1)^{n-1}u_n,u_n>0$
      - 任意项级数$\sum\limits_{n=1}^{\infty}u_n,u_n$符号无限制
  
    - 常用结论
  
  
  - 级数的收敛域
    - 有关概念
      - 函数项级数
      - 幂级数
      - 收敛点与发散点
      - 收敛域
    - 具体型问题
      - 对于不缺项幂级数$\sum\limits_{n=0}^{\infty}a_nx^n$
      - 对于缺项幂级数或一般函数项级数$\sum u_n(x)$
    - 抽象型问题
      - 阿贝尔定理
      - 结论1
      - 结论2
  - 展开问题
    - 考法
      - 函数展开
      - 积分展开
      - 导数展开
      - 无穷小比阶
    - 工具
      - 先积后导
      - 先导后积
      - 重要展开公式
  - 求和问题
    - 直接套公式
    - 用先积后导火先导后积求和函数
    - 用所给微分方程求和函数
    - 建立微分方程并求和函数
    - 综合题
  - 傅立叶级数
    - 周期为2l的傅里叶级数
    - 狄利克雷收敛定理
    - 正弦级数和余弦级数
    - 只在[0,l]上有定义的函数的正弦级数和余弦级数展开


{% endmarkmap %}

正项级数的比较判别

正项级数的比较判别的极限形式

三个重要尺度

1. 等比级数$\sum\limits^{\infty}_{n=1}aq^{n-1}, \begin{cases}|q|<1, convergence\\|q|\ge 1,divergence\end{cases}$
2. p级数$\sum\limits^{\infty}_{n=1}\frac{1}{n^p},\begin{cases}p>1, convergence\\p\le1,divergence\end{cases}$
3. 广义p级数$\sum\limits^{\infty}_{n=1}\frac{1}{n(\ln n)^p},\begin{cases}p>1, convergence\\p\le1,divergence\end{cases}$

正项级数比值判别法：=1失效，>1发散，<1收敛

正项级数根值判别法：=1失效，>1发散，<1收敛

正项级数积分判别法：正项级数和其对应的反常积分同敛散。

交错级数的莱布尼茨判别法：u极限为0，u减少，则u的级数收敛

