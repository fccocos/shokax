---
title: 第二章 数列极限
math: true
sticky: true
date: 2023-08-20 06:18:12
---

{% markmap 750px %}

- 数列极限
  - 数列极限的定义及使用
    - 定义
    - 使用
      - 是常数：$\lim\limits_{n\to\infty} x_n = A \Rightarrow A$一定是一个常数
      - 唯一性：$\lim\limits_{n\to\infty}x_n=A\Rightarrow A$唯一
      - 有界性：$\{x_n\}$有界$\Rightarrow \exists M>0, |x_n|\le M$
      - 保号性：$n\to\infty, A>0\Rightarrow x_n>0; n\to\infty, A\le0\Rightarrow x_n\le 0$
      - 收敛的充要条件：所有子列$\{x_{n_k}\}$均收敛于A
  - 数列极限的存在性与计算
    - 归结原理：$\lim\limits_{x\to x_0}f(x)=A\Rightarrow \lim\limits_{n\to\infty}=x_0,x_n\ne x_0\rightarrow\lim\limits_{n\to\infty}f(x_n)=A$
    - 直接计算法
    - 定义法（“先斩后奏”）: 构造$|x_n-a|$, 证$|x_n-a|\to 0(n\to\infty)\Rightarrow\lim\limits_{n\to\infty}x_n=a$
    - 单调有界准则(单调有界极限必存在)
      - 证什么
        - 单调：证$x_{n+1}$和$X_{n}$的关系
        - 有界：证$\exists M>0,$使得$|x_n|\le M$
      - 怎么证
        - 用已知不等式
          - $\sin x \le x\Rightarrow x_{n+1}=\sin x_n\le x_n,\{x_n\}\downarrow$
          - $e^x\ge x+1\Rightarrow x_{n+1}=e^{x_n}-1\ge x_n,\{x_n\}\uparrow$
          - $x-1\ge \ln x \Rightarrow x_{n+1}=\ln x_n +1 \le x_n,\{x_n\}\downarrow$
          - $\sqrt{ab} \le \frac{a+b}{2} \Rightarrow x_{n+1}=\sqrt{x_n(3-x_n)}\le \frac{x_n+3-x_n}{2}=\frac{3}{2},\{x_n\}\uparrow$
        - 题设给出条件来推证
    - 夹逼准则: $1.y_n\le x_n \le z_n\ 2.\lim\limits_{n\to\infty}y_n=a,\lim\limits_{n\to\infty}z_n=a\Rightarrow\lim\limits_{n\to\infty}x_n=a$
      - 证什么
        - 对$x_n$放缩: $y_n\le x_n \le z_n$
        - 取极限
      - 怎么证
        - 用基本放缩方法
          - $n\cdot u_{min}\le u_1+u_2+\cdots +u_n\le n\cdot u_{max}$
          - 当$u_i\ge0$时，$1\cdot u_{max}\le u_1+u_2+\cdots+u_n\le n\cdot u_{max}$
        - 题设给出条件来推证
    - 综合题总结
      - 用导数综合
      - 用积分综合
      - 用中值定理综合
      - 用方程（列）综合
      - 用区间（列）综合
      - 用极限综合

{% endmarkmap %}