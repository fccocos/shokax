---
title: 第二章 数据的表示和运算
math: true
date: 2023-08-20 16:07:00
---

{% markmap 750px %}

- 数据的表示和运算

  - 数制与编码

    - 进位计数制及其相互转换
      - 进位计数法
      - 不同进制数之间的相互转换
      - 真值和机器数
    - BCD码
    - 定点数的编码表示
      - 机器数的定点表示
        - 定点小数
        - 定点整数
      - 原码、补码、反码、移码

    - 整数的表示
      - 无符号整数的表示
      - 带符号整数的表示

  - 运算方法和运算电路

    - 基本运算部件
      - 一位全加器
      - 串行进位加法器
      - 并行加法器
      - 带标志加法器
      - 算术逻辑单元
    - 定点数的移位运算
      - 算术移位
      - 逻辑移位
      - 循环移位
    - 定点数的加减运算
      - 补码的加减法运算
      - 补码加减运算电路
      - 移出判别方法
        - 采用一位符号位
        - 采用双符号位
        - 采用一位符号位根据数据位的进位情况判别溢出
      - 原码的加减法运算
    - 定点数的乘除运算
      - 定点数的乘法运算
        - 原码一位乘法
        - 无符号乘法运算电路
        - 补码一位乘法（Booth算法）
      - 定点的除法运算
        - 符号扩展
        - 原码除法运算（不恢复余数法）
        - 补码除法运算（加减交替法）
    - C语言中的整数类型及类型转换
      - 有符号数和无符号数的转换
      - 不同字长整数之间的转换
    - 数据的存储和排列
      - 数据的“大端方式”和“小端方式”存储
      - 数据按“边界对齐”方式存储

  - 浮点数的表示

    - 浮点数的表示
      - 浮点数的表示格式
      - 浮点数的表示范围
      - 浮点数的规格化
      - IEE 754标准
      - 定点、浮点表示的区别
    - 浮点数的加减运算
      - 对阶
      - 尾数求和
      - 规格化
      - 舍入
      - 溢出判断
      - C语言中的浮点数类型

{% endmarkmap %}

### 原码、反码、补码、移码的总结

- 补码 = 反码+1
- 原码 = 补码取反 + 1
- 补码的符号位不参与变换
- 移码 = 真值 + 偏置值($R^n$,R表示数基，n表示真值的位数)

### 移码的特点

1. 零唯一表示。$[+0]_{shift} = 2^n +0=2^n, [-0]_{shift} = 2^n-0=2^n$
2. 移码和补码仅在符号位上相异，数值位相同。$[x_s,x_nx_{n-1}\cdots x_2x_1]_{shift}=[\overline{x_s},x_nx_{n-1}\cdots x_2x_1]_{comp}$
3. $(000\cdots 00)_{shift} = -2^n:x+2^n = 0\Rightarrow x = -2^n$

## ALU

| 标志位名称 | 标志位缩写 | 无符号运算 | 有符号运算 |                   标志位生成公式                    |                              1                               |              0               |
| :--------: | :--------: | :--------: | :--------: | :-------------------------------------------------: | :----------------------------------------------------------: | :--------------------------: |
|  零标志位  |     ZF     |   有意义   |   有意义   |     $ZF = \overline{F_{n-1}+F_{n-2}\cdots+F_0}$     |                              0                               |             非零             |
| 溢出标志位 |     OF     |   有意义   |   有意义   |      $OF = C_{out}\oplus C_{n-1}(C_{out}=C_n)$      |                         无符号数溢出                         |       无符号数没有溢出       |
| 符号标志位 |     SF     |   无意义   |   有意义   |                    $SF=F_{n-1}$                     |                        有符号数为负数                        |        有符号数为正数        |
| 进位标志位 |     CF     |   有意义   |   无意义   | $CF = C_{out}\oplus C_{in}(C_{out}=C_n,C_{in}=C_0)$ | 当$C_{in}=1,C_{out}=0$时，无符号数借位；<br>当$ C_{in}=0,C_{out}=1$时，无符号数进位 | 无符号数既没有进位也没有借位 |

==加法器的本质是无符号数之间的加法运算，而无符号数之间的减法运算或有符号数之间的加减运算的实现是通过将参与运算的数转换为补码之间的加法运算来实现的。==

### 溢出判别

本质：

1. 两个符号相同的数相加
2. 两个符号相异的数相减

#### 方法一：采用一位符号位

只要运算结果的符号位与原操作数的符号位互异，则说明运算结果发生溢出。

设A的符号位为$A_s$, B的符号位为$B_s$，C(运算结果)的符号位为$C_i$, 溢出标志位为V，则溢出逻辑表达式为$V = A_sB_s\overline{C_s}+\overline{A_s}\cdot\overline{B_s}\cdot C_s$。若V=0，则没有溢出；若V=1，则表示有溢出。

#### 方法二：采用两位符号位（模4补码）

运算结果的两个符号为$S_{S_1}S_{S_2}$，如果$S_{S_1}S_{S_2}$相同，则表示未溢出；否则，表示溢出。而此时正真的符号位为$S_{S_1}$.

1. $S_{S_1}S_{S_2} = 00$ 表示结果为正，没有溢出
2. $S_{S_1}S_{S_2}=01$ 表示结果正溢出
3. $S_{S_1}S_{S_2}=10$ 表示结构负溢出
4. $S_{S_1}S_{S_2}=11$ 表示结果为负，没有溢出

溢出逻辑表达式为$V=S_{S_1}\oplus S_{S_2}$, V=1表示溢出，V=0表示没有溢出。

#### 方法三：采用一位符号位根据数据位的进位情况判断溢出

如果符号位的进位与最好位数的进位相同，则没有溢出，否则溢出。

溢出逻辑表达式位$V=C_s\oplus C_{high},C_s=C_n, C_{high}=C_{n-1}$，V=1，则溢出；V=0，则未溢出。

### 浮点数

#### IEEE754标准

![IEEE754标准浮点数格式](https://gitee.com/fangcongss/blog-pic/raw/master/img/IEEE754%E6%A0%87%E5%87%86%E6%B5%AE%E7%82%B9%E6%95%B0%E6%A0%BC%E5%BC%8F.png)

32位的偏置值为127=$2^7-1$；64位的偏置值位1023=$2^{10}-1$

IEEE754标准32单精度浮点数真值公式：$X=(-1)^S\times1.M\times2^{E-127}$

IEEE754标准64位双精度浮点数真值公式：$Y=(-1)^{S}\times1.M\times2^{E-1023}$

- 当E=0且M=0，即阶码为1111 110，尾码为$\underbrace{00\cdots 0}_{24}$时，真值为0
- 当E=0且$M\ne0$时，此时为非规格化数,其真值表示式为$(-1)^S\times0.M\times2^{-126}$
- 当$1\le E\le254$时，此时为规格化数，其真值为$(-1)^S\times1.M\times2^{E-127}$
- 当E=255且$M\ne 0$时，此时真值为NaN(非数值)
- 当E=255且M=0时，此时真值为正无穷或负无穷

IEEE754标准32单精度浮点数的最小值为M=0,E=1,X=$1.0\times2^{-126}$, 最大值为E=254,M=$.\underbrace{11\cdots1}_{24}$, X=$1.\underbrace{11\cdots1}_{24}\times2^{254-127}=(2-2^{-23})\times2^{127}$

IEEE754标准32单精度浮点数的取值范围为$[-(2-2^{-23})\times2^{127},-2^{-126}]\cup0\cup[2^{-126},(2-2^{-23})\times2^{127}]$

![IEEE754标准单精度取值范围](https://gitee.com/fangcongss/blog-pic/raw/master/img/IEEE754%E6%A0%87%E5%87%86%E5%8D%95%E7%B2%BE%E5%BA%A6%E5%8F%96%E5%80%BC%E8%8C%83%E5%9B%B4.png)

#### 浮点数的运算

1. 对阶（小阶向大阶看齐）
2. 尾数求和
3. 规格化（对所求结果进行规格化）
4. 舍入
5. 判断溢出
