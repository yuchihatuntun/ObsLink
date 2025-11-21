---
title: VLSI-Lecture-07
date: 2025-11-21
description: Combinational logic, covering static logic (including static complementary CMOS inverters, ratioed logic, and pass-transistor logic) and dynamic logic (including principles, domino logic, etc., as well as signal integrity issues)
tags:
  - 2025-autumn
  - VLSI
  - Notebook
image: "[[attachments/cover-06.png]]"
imageAlt: Young Girls and Integrated Circuits
imageOG: false
hideCoverImage: false
hideTOC: false
targetKeyword: ""
draft: false
aliases:
  - 未命名
---
### 静态逻辑
#### 静态互补 CMOS 反相器

**回顾：**

由电流相等：
$$ k_n' V_{DSATn} \left( V_M - V_{Tn} - \frac{V_{DSATn}}{2} \right) + k_p' V_{DSATp} \left( V_M - V_{DD} - V_{Tp} - \frac{V_{DSATp}}{2} \right) = 0 $$
可以推导得到开关阈值$V_M$表达式： $$ V_M = \frac{\left( V_{Tn} + \frac{V_{DSATn}}{2} \right) + \left( V_{DD} + V_{Tp} + \frac{V_{DSATp}}{2} \right) r}{1 + r}, \quad r = \frac{k_p' V_{DSATp}}{k_n' V_{DSATn}} = \frac{\mu_{p} W_p}{\mu_{n} W_n} $$改变$W_p/W_n$（即$r$，通常为$2$）会平移电压传输特性曲线（VTC），$r$增大则$V_M$右移；互补CMOS静态反相器的$V_M$对器件参数不敏感。

当阈值电压$V_M$恰好等于$\frac{V_{DD}}{2}$时，噪声容限最大，

#### 有比逻辑

#### 传输管逻辑

### 动态逻辑

#### 基本原理
![](attachments/动态门的基本原理.png)



#### 串联动态门

#### 动态逻辑的速度和功耗

#### 动态设计中的信号完整性问题

### 电路选择指南