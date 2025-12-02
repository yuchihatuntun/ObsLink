---
title: Chapter-05
date: 2025-11-29
description: ""
tags:
  - 2025-autumn
  - Semiconductor-Device-Physics
  - Exercise
image: "[[attachments/cover-22.png]]"
imageAlt: ""
imageOG: false
hideCoverImage: false
hideTOC: false
targetKeyword: ""
draft: true
aliases:
  - 未命名
---
# 5.1 双级晶体管的工作原理

>**12.1** 
>对于处于热平衡状态下的均匀掺杂 $n^{++}p^{+}n$ 双极晶体管。
>
>(a) 画出其能带图；
>
>(b) 画出器件的电场分布情况；
>
>(c) 假设该管工作于正向有源状态，重做 (a)(b)。

(a)

![](attachments/BJT-零偏-热平衡能带图.png)
*BJT零偏热平衡能带图*

(b)



>**12.2** 
>对于 $p^{++}n^{+}p$ 的双极晶体管，画出其处于以下状态下的能带图；
>
>(a) 热平衡状态；
>
>(b) 正向有源区；
>
>(c) 反向有源区；
>
>(d) B-E 结和 B-C 结均为反偏，晶体管处于截止区时。



>**12.3** 
>npn 型 Si 的双极晶体管，其基极参数如下：$D_{n}=18 \text{cm}^{2}/\text{s}$ ，$n_{B0}=4\times10^{3} \text{cm}^{-3}$ ，$x_{B}=0.80 \mu \text{m}$ ，$A_{BE}=5\times10^{-5} \text{cm}^{2}$ 。
>
>(a) 比较式 (12.1) 和式 (12.2)，估算 $I_{s}$；
>
>(b) 当 $v_{BE}$ 分别等于 0.58 V，0.65 V，0.72 V 时，计算集电极电流。

**(a)** 根据题干中参考的两个式子：

$$
i_{C}=\frac{-eD_{n}A_{BE}}{x_{B}}\cdot n_{B0}\exp\left(\frac{\nu_{BE}}{V_{t}}\right)\tag{12.1}
$$
$$
i_{C}=I_{s}\exp\left(\frac{\nu_{BE}}{V_{t}}\right)\tag{12.2}
$$
容易得到反相器电流公式：
$$
I_{S} = \frac{e D_{n} A_{BE} n_{B0}}{x_{B}}
$$

代入数值：
$$
I_{S} = \frac{(1.6 \times 10^{-19})(18)(5 \times 10^{-5})(4 \times 10^{3})}{0.80 \times 10^{-4}}
$$

结果：
$$
I_{S} = 7.2 \times 10^{-15} \text{ A}
$$

**(b)**  根据（12.2）的集电极电流公式：
$$
I_{C} = I_{S} \exp\left(\frac{v_{BE}}{V_{t}}\right)
$$

(i)  $v_{BE} = 0.58$ V 时：
$$
I_{C} = (7.2 \times 10^{-15}) \exp\left(\frac{0.58}{0.0259}\right) = 3.827 \times 10^{-5} \text{ A} = 38.27 \mu\text{A}
$$

(ii)  $v_{BE} = 0.65$ V 时：
$$
I_{C} = (7.2 \times 10^{-15}) \exp\left(\frac{0.65}{0.0259}\right) = 5.710 \times 10^{-4} \text{ A} = 0.571 \text{ mA}
$$

(iii)  $v_{BE} = 0.72$ V 时：
$$
I_{C} = (7.2 \times 10^{-15}) \exp\left(\frac{0.72}{0.0259}\right) = 8.519 \times 10^{-3} \text{ A} = 8.519 \text{ mA}
$$


>**12.4** 
>
>npn 双极晶体管参数如下：$D_{n}=22 \text{ cm}^{2}/\text{s}$，$n_{B0}=2\times10^{4} \text{ cm}^{-3}$，$x_{B}=0.80 \mu \text{m}$，
>
>(a) 若要求 $v_{BE}=0.60 \text{ V}$ 时，$i_{c}=2 \text{ mA}$，则 $A_{BE}$ 应为多少？
>
>(b) 利用 (a) 的结果，$i_{c}=5 \text{ mA}$，则 $v_{BE}$ 应为多少？

(a) 集电极电流：
$$
I_{C} = \frac{eD_{n}A_{BE}}{x_{B}} \cdot n_{B0} \cdot \exp\left(\frac{v_{BE}}{V_{t}}\right)
$$

代入数值：
$$
2 \times 10^{-3} = \frac{(1.6 \times 10^{-19})(22)A_{BE}}{0.80 \times 10^{-4}} \times (2 \times 10^{4}) \exp\left(\frac{0.60}{0.0259}\right)
$$

解得==基极-发射极结面积==：
$$
A_{BE} = 1.975 \times 10^{-4} \text{ cm}^{2}
$$

(b) 公式同上，代入数值：
$$
5 \times 10^{-3} = \frac{(1.6 \times 10^{-19})(22)(1.975 \times 10^{-4})}{0.80 \times 10^{-4}} \times (2 \times 10^{4}) \exp\left(\frac{v_{BE}}{0.0259}\right)
$$

基极-发射极电压：
$$
v_{BE} = (0.0259) \ln\left(\frac{5 \times 10^{-3}}{1.738 \times 10^{-13}}\right)
$$

最终得到：
$$
v_{BE} = 0.6237 \text{ V}
$$

>**12.5** 
>
>在习题 12.3 中，
>
>(a) 若 $\alpha=0.9850$，求共发射极电流增益 $\beta=\alpha/(1-\alpha)$；
>
>(b) 求习题 12.3 中对应的发射极和基极电流；
>
>(c) 假设 $\alpha=0.9940$，重做 (a) 和 (b)。

(a) 根据题干的公式：
$$
\beta = \frac{\alpha}{1 - \alpha} = \frac{0.9850}{1 - 0.9850} = 65.7
$$

(b) 针对不同增益的计算：

(i) 当 $I_{C} = 38.27\ \mu\text{A}$ 时：
$$
I_{B} = \frac{I_{C}}{\beta} = \frac{38.27}{65.67} = 0.5828\ \mu\text{A}
$$
$$
I_{E} = \frac{I_{C}}{\alpha} = \frac{38.27}{0.9850} = 38.85\ \mu\text{A}
$$

(ii) 当 $I_{C} = 0.571\ \text{mA}$ 时：
$$
I_{B} = \frac{0.571}{65.67} = 0.008695\ \text{mA} = 8.695\ \mu\text{A}
$$
$$
I_{E} = \frac{0.571}{0.9850} = 0.5797\ \text{mA}
$$

(iii) 当 $I_{C} = 8.519\ \text{mA}$ 时：
$$
I_{B} = \frac{8.519}{65.67} = 0.1297\ \text{mA}
$$
$$
I_{E} = \frac{8.519}{0.9850} = 8.649\ \text{mA}
$$

(c) 共发射极电流增益的计算公式为：
$$
\beta = \frac{\alpha}{1 - \alpha} = \frac{0.9940}{1 - 0.9940} = 165.7
$$

(i) 当 $I_{C} = 38.27\ \mu\text{A}$ 时：
$$
I_{B} = \frac{38.27}{165.7} = 0.2310\ \mu\text{A}
$$
$$
I_{E} = \frac{38.27}{0.9940} = 38.50\ \mu\text{A}
$$

(ii) 当 $I_{C} = 0.571\ \text{mA}$ 时：
$$
I_{B} = \frac{0.571}{165.7} = 0.003446\ \text{mA} = 3.446\ \mu\text{A}
$$
$$
I_{E} = \frac{0.571}{0.9940} = 0.5744\ \text{mA}
$$

(iii) 当 $I_{C} = 8.519\ \text{mA}$ 时：
$$
I_{B} = \frac{8.519}{165.7} = 0.05141\ \text{mA} = 51.41\ \mu\text{A}
$$
$$
I_{E} = \frac{8.519}{0.9940} = 8.570\ \text{mA}
$$

>**12.6** 
>
>工作在正向有源区的双极晶体管，
>
>(a) 假设 $I_{B}=4.2 \mu \text{A}$，$I_{C}=0.625 \text{ mA}$，求 (i) $\beta$，(ii) $\alpha$ 和 (iii) $I_{E}$；
>
>(b) 假设 $I_{E}=1.273 \text{ mA}$，$I_{C}=1.254 \text{ mA}$，求 (i) $\beta$，(ii) $\alpha$ 和 (iii) $I_{B}$；
>
>(c) 假设 $I_{B}=0.065 \mu \text{A}$，$\beta=150$，求 $\alpha$，$I_{C}$，$I_{E}$。

(a) 共射极电流增益：
$$
\beta = \frac{I_C}{I_B} = \frac{0.625}{0.0042} = 148.8
$$

则共基极电流增益：
$$
\alpha = \frac{\beta}{1 + \beta} = \frac{148.8}{149.8} = 0.9933
$$

发射极电流：
$$
I_E = \frac{I_C}{\alpha} = \frac{0.625}{0.9933} = 0.6292\ \text{mA}
$$

(b) 共基极电流增益：
$$
\alpha = \frac{I_C}{I_E} = \frac{1.254}{1.273} = 0.9851
$$

共发射极电流增益：
$$
\beta = \frac{\alpha}{1 - \alpha} = \frac{0.9851}{1 - 0.9851} = 66.0
$$

基极电流：
$$
I_B = \frac{I_C}{\beta} = \frac{1.254}{66} = 0.0190\ \text{mA} = 19.0\ \mu\text{A}
$$

(c) 共基极电流增益：
$$
\alpha = \frac{150}{151} = 0.99338
$$

计算集电极电流：

$I_C = \beta I_B = (150)(0.065) = 9.75\ \mu\text{A}$

计算发射极电流：

$I_E = (1 + \beta) I_B = (151)(0.065) = 9.815\ \mu\text{A}$

>**12.7** 
>假设 npn 双极晶体管的 $\beta=100$。
>
>(a) 画出其理想的 $i_{C}$ 特性曲线 $v_{CE}$ 在 $0\sim10 \text{ V}$ 范围内变化，$i_{B}$ 以 0.01 mA 的步长从 $0\sim0.1 \text{ mA}$ 变化；
>
>(b) 假设在图 12.8 所示电路中，$V_{CC}=10 \text{ V}$，$R_{C}=1 \text{ k}\Omega$，在 (a) 的晶体管特性曲线上加上负载线；
>
>(c) 在图上标出 $i_{B}=0.05 \text{ mA}$ 时对应的 $i_{C}$，$v_{CE}$ 的值。

![](attachments/ScDP-exercise-ch05-12-07.png)

>**12.8** 
>如图 12.8 所示，假设 $V_{CC}=3 \text{ V}$，$V_{BE}=0.65 \text{ V}$。
>
>(a) 假设 $R_{C}=25 \text{ k}\Omega$，(i) 画出 $I_{C}$ 随 $V_{CE}$ 变化的曲线，$V_{CE}$ 在 0.20 V 到 3 V 之间，(ii) $I_{C}$ 是多少时，$V_{CB}$ 才能为 0？
>
>(b) $R_{C}=10 \text{ k}\Omega$ 时，重做 (a)。

# 5.2 少子的分布

>**12.9**
>
> 一个均匀掺杂的npn硅双极晶体管工作于正向有源区。$T = 300K$，晶体管掺杂浓度为$N_{E} = 8\times10^{17}cm^{-3}$，$N_{B} = 2\times10^{16}cm^{-3}$，$N_{C} = 10^{15}cm^{-3}$。
> 
> (a)求热平衡时的$n_{B0}$，$p_{E0}$和$p_{C0}$；
> 
> (b)$V_{BE} = 0.640V$时，计算$x = 0$处的$n_{B}$和$x^{\prime} = 0$处的$p_{E}$；
> 
> (c)画出器件内的少子浓度分布情况并对每条线加标注。

(a) 经典计算==平衡少子==

发射极区平衡少子空穴浓度：
$$
p_{E0} = \frac{n_{i}^{2}}{N_{E}} = \frac{(1.5 \times 10^{10})^{2}}{8 \times 10^{17}}
$$
$$
p_{E0} = 2.8125 \times 10^{2} \text{ cm}^{-3}
$$

基极区平衡少子电子浓度：
$$
n_{B0} = \frac{n_{i}^{2}}{N_{B}} = \frac{(1.5 \times 10^{10})^{2}}{2 \times 10^{16}}
$$
$$
n_{B0} = 1.125 \times 10^{4} \text{ cm}^{-3}
$$

集电极区平衡少子空穴浓度：
$$
p_{C0} = \frac{n_{i}^{2}}{N_{C}} = \frac{(1.5 \times 10^{10})^{2}}{10^{15}}
$$
$$
p_{C0} = 2.25 \times 10^{5} \text{ cm}^{-3}
$$

(b) ==正向有源模式==的边界条件求解

![](attachments/BJT内部坐标结构.png)

基极区 $x = 0$ 处的少子电子浓度：

书上给的非平衡少子浓度公式是：
$$
\delta n_B(0) = n_B(x=0) - n_{B0} = n_{B0}\left[ \exp\left( \frac{eV_{BE}}{kT} \right) - 1 \right]
$$
求解的是全部少子浓度，所以是前一项：
$$
n_{B}(0) = n_{B0} \exp\left(\frac{V_{BE}}{V_{t}}\right) = (1.125 \times 10^{4}) \exp\left(\frac{0.640}{0.0259}\right)
$$
$$
n_{B}(0) = 6.064 \times 10^{14} \text{ cm}^{-3}
$$
同理，

$$
\delta p_E(0) = p_E(x' = 0) - p_{E0} = p_{E0}\left[ \exp\left( \frac{eV_{BE}}{kT} \right) - 1 \right]
$$

发射极区 $x^{\prime} = 0$ 处的少子空穴浓度：

$$ p_{E}(0) = p_{E0} \exp\left(\frac{V_{BE}}{V_{t}}\right) = (2.8125 \times 10^{2}) \exp\left(\frac{0.640}{0.0259}\right) $$
$$
p_{E}(0) = 1.516 \times 10^{13} \text{ cm}^{-3}
$$


>**12.10** 
>$T = 300K$时的硅==pnp==双极晶体管，均匀掺杂，工作在正向有源区。掺杂浓度为$N_{E} = 5\times10^{17}cm^{-3}$，$N_{B} = 10^{16}cm^{-3}$，$N_{C} = 10^{15}cm^{-3}$。
>
>(a)求热平衡时的$n_{E0}$，$p_{B0}$，$n_{C0}$；
>
>(b)$V_{EB} = 0.615V$时，计算$x = 0$处的$p_{B}$和$x^{\prime} = 0$处的$n_{E}$；
>
>(c)画出器件内的少子浓度分布情况并对每条线加标注。

(a) 

>[!danger] 注意管子换极性了，三个待求浓度还是少子浓度。

射极平衡少子电子浓度：
$$
n_{E0} = \frac{n_{i}^{2}}{N_{E}} = \frac{(1.5 \times 10^{10})^{2}}{5 \times 10^{17}}
$$
$$
n_{E0} = 4.5 \times 10^{2} \text{ cm}^{-3}
$$
基极平衡少子空穴浓度：
$$
p_{B0} = \frac{n_{i}^{2}}{N_{B}} = \frac{(1.5 \times 10^{10})^{2}}{10^{16}}
$$
$$
p_{B0} = 2.25 \times 10^{4} \text{ cm}^{-3}
$$

集电极平衡少子电子浓度：
$$
n_{C0} = \frac{n_{i}^{2}}{N_{C}} = \frac{(1.5 \times 10^{10})^{2}}{10^{15}}
$$
$$
n_{C0} = 2.25 \times 10^{5} \text{ cm}^{-3}
$$

(b) 原理同 **12.9**

基极区 $x = 0$ 处的少子空穴浓度：
$$
p_{B}(0) = p_{B0} \exp\left(\frac{V_{EB}}{V_{t}}\right)
$$
$$
= (2.25 \times 10^{4}) \exp\left(\frac{0.615}{0.0259}\right)
$$
$$
p_{B}(0) = 4.62 \times 10^{14} \text{ cm}^{-3}
$$

射极区 $x^{\prime} = 0$ 处的少子电子浓度：
$$
n_{E}(0) = n_{E0} \exp\left(\frac{V_{EB}}{V_{t}}\right)
$$
$$
= (4.5 \times 10^{2}) \exp\left(\frac{0.615}{0.0259}\right)
$$
$$
n_{E}(0) = 9.24 \times 10^{12} \text{ cm}^{-3}
$$
(c)

![](attachments/pnp-正向有源区-少子分布图.png)

>**12.11** 
>$T = 300K$时，一个均匀掺杂的pnp硅双极晶体管工作于正向有源区，$V_{CB} = 2.5V$，基区宽度$x_{B0} = 1.0\mu m$，掺杂浓度为$N_{E} = 8\times10^{17}cm^{-3}$，$N_{B} = 2\times10^{16}cm^{-3}$，$N_{C} = 10^{15}cm^{-3}$。
>
>(a)确定B-E电压，使得$x = 0$处少子电子浓度$n_{B}$是10%的多子空穴浓度；
>
>(b)确定在这个偏压下$x^{\prime} = 0$处少子空穴的浓度。



>**12.12** 
>考虑式(12.15a)中npn双极晶体管基区的少子电子浓度，在本题中要比较B-C结和B-E结中的电子浓度的变化，特别地，请计算出$x_{B}/L_{B} = 0.1$，$x_{B}/L_{B} = 1.0$和$x_{B}/L_{B} = 10$三种情况下，$x = x_{B}$处的$d(\delta n_{B})/dx$和$x = 0$处的$d(\delta n_{B})/dx$之比。



>**12.13** 
>试给出式(12.14a)和式(12.14b)的表达式。



>**12.14** 
>试推导出均匀掺杂pnp双极晶体管在正向有源工作区的基极剩余少子空穴浓度。

类比书上的步骤求解一遍连续性方程。



# 5.3 低频共基极电流增益



# 5.4 非理想效应



# 5.5 等效电路模型


