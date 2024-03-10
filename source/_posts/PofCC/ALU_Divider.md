---
title: 除法器
categories:
  - 计算机组成原理
tag:
  - 计算机组成原理
  - - 计算机组成原理
    - ALU
  - - 计算机组成原理
    - ALU
    - 除法器
valine: true
math: true
abbrlink: 39f4e8b6
date: 2023-06-12 12:09:39
---

## 原码除法运算（不恢复余数法）

### 运算原则

1. 商符和商值分开进行
2. 减法操作用补码加法实现
3. 商符由被除数和除数的符号位`异或`形成

即：$Q_S = X_S \oplus Y_S;\, |Q|=|X|/|Y|$

### 运算步骤

1. $R=|X|-|Y|=|X|+[-|Y|]_{comp},$R为部分余数。
2. 当R<0时，商Q上0，余数R和商Q左移一位，余数R再加上除数|Y|$(R = R+|Y|)$；当R>0时，商Q上1，余数R和商Q左移一位，余数R再减去除数|Y|$(R=R+[-|Y|]_{comp})$
3. 当第n+1步余数为负数时，需加上除数|X|得到第n+1步正确的余数R（余数和商的符号相同）

### 流程图

![不恢复余数法](https://gitee.com/fangcongss/blog-pic/raw/master/img/%E4%B8%8D%E6%81%A2%E5%A4%8D%E4%BD%99%E6%95%B0%E6%B3%95-20230612164630539.png)

### 举例说明

>设x=0.1011, y=0.1101, 采用原码加减交替法求x/y

![除法实例](https://gitee.com/fangcongss/blog-pic/raw/master/img/%E9%99%A4%E6%B3%95%E5%AE%9E%E4%BE%8B.png)

## 补码除法运算

### 运算原则

1. 符号位参与运算，所有的数都用补码的形式
2. 除法第一步：根据被除数和除数的符号位进行加减，同号相加，异号相减，获取的余数
3. 余数和除数同号，商上1，余数和商左移一位，余数与除数相减；余数和除数异号，商上0，余数和商左移一位，余数与除数相加。
4. 商采用恒置“1”法进行舍入。



### 运算步骤

1. 初始化商$Q$,余数$R$,被除数$X$, 除数$Y$。

2.  计算所有数的补码$X_{comp}, Y_{comp},[-Y]_{comp}$。

3. 除法第一步：

   - 如果$X_S\oplus Y_S = 0$，则$R_{comp} = X_{comp}+Y_{comp}$；

   - 如果$X_S\oplus Y_S = 1$，则$R_{comp} = X_{comp}+[-Y]_{comp}$。

4. 除法第二步：

   - 如果$R_S\oplus Y_S = 0$，则$Q_{comp}+=1, Q_{comp}<<1, R_{comp}<<1,R_{comp}+=[-Y]_{comp}$；
   - 如果$R_S\oplus Y_S = 1$，则$Q_{comp} += 0, Q_{comp}<<1, R_{comp}<<1,R_{comp}+=Y_{comp}$。

5. 重复第二步n次

6. 除法第n+1步：将商Q采用恒置“1”法进行舍入

### 流程图

![有符号除法](https://gitee.com/fangcongss/blog-pic/raw/master/img/%E6%9C%89%E7%AC%A6%E5%8F%B7%E9%99%A4%E6%B3%95.png)

###  注意事项

1. 一般而言，补码采用双符号位（余4码）
