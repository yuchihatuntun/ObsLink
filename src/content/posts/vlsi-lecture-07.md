---
title: VLSI-Lecture-07
date: 2025-11-21
description: Combinational logic, covering static logic (including static complementary CMOS inverters, ratioed logic, and pass-transistor logic) and dynamic logic
tags:
  - 2025-autumn
  - VLSI
  - Notebook
image: "[[attachments/cover-06.png]]"
imageAlt: Young Girls and Integrated Circuits
imageOG: true
hideCoverImage: false
hideTOC: false
targetKeyword: vlsi combined logic circuit
draft: false
---
# 静态逻辑
## 静态互补 CMOS 反相器

**回顾：**

由电流相等：
$$ k_n' V_{DSATn} \left( V_M - V_{Tn} - \frac{V_{DSATn}}{2} \right) + k_p' V_{DSATp} \left( V_M - V_{DD} - V_{Tp} - \frac{V_{DSATp}}{2} \right) = 0 $$
可以推导得到开关阈值$V_M$表达式： $$ V_M = \frac{\left( V_{Tn} + \frac{V_{DSATn}}{2} \right) + \left( V_{DD} + V_{Tp} + \frac{V_{DSATp}}{2} \right) r}{1 + r}, \quad r = \frac{k_p' V_{DSATp}}{k_n' V_{DSATn}} = \frac{\mu_{p} W_p}{\mu_{n} W_n} $$改变$W_p/W_n$（即$r$，通常为$2$）会平移电压传输特性曲线（VTC），$r$增大则$V_M$右移；互补CMOS静态反相器的$V_M$对器件参数不敏感。

当阈值电压$V_M$恰好等于$\frac{V_{DD}}{2}$时，噪声容限最大，

## 有比逻辑

## 传输管逻辑

# 动态逻辑

## 基本原理
![](attachments/动态门的基本原理.png)

1. **预充电阶段**（时钟信号 $CLK = 0$）：

	- **预充电管导通**：PMOS预充电管（$M_p$）在栅极低电平作用下导通，建立了电源 $V_{DD}$ 到输出节点 $Out$ 的低阻抗路径（无论输入逻辑状态如何，输出节点 $Out$ 均被无条件充电至高电平 $V_{DD}$）。
	    
	- **求值管关断**：NMOS求值管（$M_e$）在栅极低电平作用下截止（Cut-off），切断了下拉网络（PDN）与地（GND）之间的物理连接（电源 $V_{DD}$ 与地之间也不存在直流通路。因此，该机制消除了在预充电期间可能发生的任何静态功耗）。
2. **求值阶段**（时钟信号 $CLK = 1$）

	- **预充电管关断**：PMOS预充电管（$M_p$）截止，断开了输出节点与电源 $V_{DD}$ 的连接。
	    
	- **求值管导通**：NMOS求值管（$M_e$）导通，将下拉网络（PDN）的底部接入地（GND）。此时，电路的输出状态完全取决于下拉逻辑网络（PDN）的导通情况。

3. **有条件放电（求值阶段）**

- 情形一：输入逻辑使得PDN导通
    
    如果在输入信号作用下，下拉网络形成导通路径，则输出节点 $Out$ 通过PDN和导通的求值管 $M_e$ 形成到地的低阻抗通路。存储在输出节点的电荷被泄放，输出电压降至逻辑“0”（GND）。
    
- 情形二：输入逻辑使得PDN关断
    
    如果下拉网络未形成通路，输出节点无法放电。此时，预充电的高电平值（$V_{DD}$）被维持在负载电容 $C_L$ 上。

## 串联动态门

## 动态逻辑的速度和功耗

## 动态设计中的信号完整性问题

# 电路选择指南