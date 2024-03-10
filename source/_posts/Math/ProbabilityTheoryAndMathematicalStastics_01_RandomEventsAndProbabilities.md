---
title: 第一章 随机事件和概率
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
date: 2023-08-18 09:55:08
---

{% markmap 750px %}

- 第一章 随机事件和概率
  - 古典概型
    - 随机分配问题（盒中放球）
    - 简单随机抽样问题（盒中取球）
  - 几何概型
    - $P(A)=\frac{A}{S}$，A表示A的度量（长度，面积），S表示S的度量（长度、面积）
  - 重要概率公式
    - 对立
      - 长杠变短杠，开口换方向
      - $P(A)= 1-P(\overline{A})$
    - 互斥
      - $A\cup B = A\cup\overline{A}B=B\cup A\overline{B}=A\overline{B}\cup AB\cup \overline{A}B$
      - $B_1,B_2,B_3$为完备事件组，则$A=AB_1\cup AB_2\cup AB_3$
      - $P(A\overline{B})=P(A-B)=P(A)-P(AB)$
      - $P(A+B) = P(A)+P(B)-P(AB)$
      - $P(A+B+C) = P(A)+P(C)+P(C)-P(AB)-P(AC)-P(BC)+P(ABC)$
      - 若$A_1,A_2,\cdots,A_n$两两互斥，则$P(\bigcup_{i=1}^n A_i)=\sum_{i=1}^n P(A_i)$ 
    - 独立
      - $P(A_1A_2\cdots A_n)=P(A_1)P(A_2)\cdots P(A_n)$
      - $P(\bigcup_{i=1}^n A_i)=1-\Pi_{i=1}^n [1-P(A_i)]$
    - 条件
      - $P(A|B) = \frac{P(AB)}{P(B)}$
      - 全概率公式：$P(B) = \sum_{i=1}^nP(A_i)P(B|A_i)$
      - 贝叶斯公式：$P(A_j|B) = \frac{P(A_jB)}{P(B)} = \frac{P(A_j)P(A_j|B)}{\sum_{i=1}^n P(A_i)P(B|A_i)} $
    - 不等式或包含
      - $0 \le p \le 1$
      - $A\subseteq B \Rightarrow P(A)\le P(B)$
      -  $AB \subseteq A \subseteq A+b \Rightarrow P(AB)\le P(A) \le P(A+B)$
    - 最值
      - $\{\max\{X, Y\}\le a\}=\{X\le a\}\cap\{Y\le a\}$
      - $\{\max\{X, Y\}>a\}=\{X>a\}\cup\{Y>a\}$
      - $\{\min\{X, Y\}\le a\} = \{X\le a\}\cup\{Y\le a\}$
      - $\{\min\{X, Y\}>a\}=\{X>a\}\cap\{Y>a\}$
      - $\{\max\{X,Y\}\le a\}\subseteq \{\min\{X,Y\}\le a\}$
      - $\{\min\{X, Y\}>a\}\subseteq\{\max\{X,Y\}>a\}$
  - 事件独立性的判断
    - 定义：$P(AB)=P(A)P(B) \Leftrightarrow$A,B独立
    - 判定：
      - $P(AB)=P(A)P(B)\Leftrightarrow P(A\overline{B})=P(A)P(\overline{B})\Leftrightarrow P(\overline{A}B)=P(\overline{A})P(B)\Leftrightarrow P(\overline{AB})=P(\overline{A})P(\overline{B})$
      - 对独立事件组不含相同事件作运算，得到的新事件组依然独立
      - $P(A)>0,P(AB)=P(A)P(B)\Leftrightarrow P(B|A)=P(B)$
      - $0<P(A)<1, P(AB)=P(A)P(B)\Leftrightarrow P(B|A)=P(B|\overline{A})\Leftrightarrow P(B|A) + P(\overline{B}|\overline{A})=1$
      - $P(A)=0 or P(A)=1 \Rightarrow P(AB)=P(A)P(B)$（B为任意事件）

{% endmarkmap %}
